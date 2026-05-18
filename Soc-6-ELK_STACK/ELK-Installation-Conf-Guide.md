# ELK + Filebeat Installation & Configuration Guide

## 1. Overview
- Goal: Collect logs from Linux hosts (syslog, auth.log, auditd) with Filebeat and ship them to Elasticsearch; visualize in Kibana. Logstash is optional if you need parsing or enrichment pipeline.
- Components and roles:
  - Elasticsearch: stores and indexes logs.
  - Kibana: visualizes and manages stack.
  - Filebeat: lightweight agent that reads log files and sends to Elasticsearch or Logstash.
  - Logstash (optional): centralized ingestion pipeline for parsing/enrichment.

## 2. Prerequisites
- A Linux host (or VMs) for Elasticsearch + Kibana (can be same machine for small setups).
- Ports: Elasticsearch 9200, Kibana 5601, Logstash 5044 (if used).
- Java is bundled with recent Elasticsearch packages; ensure compatibility with chosen versions.
- Decide on security: production should enable xpack security (TLS + auth). For testing you may disable it (see Security section).

## 3. Install Elasticsearch
- Download & install (Debian/Ubuntu): `dpkg -i elasticsearch-<version>-amd64.deb` or use the apt repository.
- Basic `/etc/elasticsearch/elasticsearch.yml` minimal settings for single-node:
  - `cluster.name: my-application`
  - `node.name: node-1`
  - `network.host: 0.0.0.0` (or a specific IP)
  - `discovery.type: single-node`
- Start and enable:
  - `sudo systemctl enable --now elasticsearch`
- Verify running:
  - `curl -u elastic https://localhost:9200/` (if security enabled)
  - `curl http://localhost:9200/` (if security disabled)

## 4. Elasticsearch Security
- Recommended (production): enable xpack security, configure TLS on transport and HTTP, set passwords for built-in users, and use secure certificates.
- Quick testing (not recommended for production): disable security temporarily by editing `/etc/elasticsearch/elasticsearch.yml`:
  - `xpack.security.enabled: false`
  - `xpack.security.transport.ssl.enabled: false`
  - `xpack.security.http.ssl.enabled: false`
  - Then restart Elasticsearch.
- To set/reset the elastic password when security is enabled:
  - `sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic`

## 5. Install Kibana
- Install the Kibana package matching the Elasticsearch version.
- Configure `/etc/kibana/kibana.yml` with minimal settings:
  - `server.port: 5601`
  - `server.host: 0.0.0.0` (or specific IP)
  - `elasticsearch.hosts: ["http://localhost:9200"]` (use https if ES TLS enabled)
  - `elasticsearch.username: "kibana_system"`
  - `elasticsearch.password: "<kibana_system_password>"` (if security enabled)
- Optional: enable Kibana HTTPS:
  - `server.ssl.enabled: true`
  - `server.ssl.certificate: /path/to/server.crt`
  - `server.ssl.key: /path/to/server.key`
- Start and enable:
  - `sudo systemctl enable --now kibana`
- Verify:
  - `sudo journalctl -u kibana -f`
  - Open `http://<kibana_ip>:5601`

## 6. Optional Logstash
- Install Logstash package.
- Create pipeline configs in `/etc/logstash/conf.d/` using input -> filter -> output.
- Test config:
  - `sudo /usr/share/logstash/bin/logstash --config.test_and_exit -f /etc/logstash/conf.d/`
  - Expected output: `Configuration OK`
- Start and enable:
  - `sudo systemctl enable --now logstash`

## 7. Install Filebeat
- Download and install Filebeat (example on Ubuntu):
  - `curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-9.4.0-amd64.deb`
  - `sudo dpkg -i filebeat-9.4.0-amd64.deb`
- Enable and start:
  - `sudo systemctl enable --now filebeat`

## 8. Configure Filebeat Inputs
Edit `/etc/filebeat/filebeat.yml` and add the inputs you need. `filestream` is modern and efficient, but `log` works fine too.

```yaml
filebeat.inputs:
- type: log
  enabled: true
  paths:
    - /var/log/syslog
  fields:
    log_type: syslog

- type: log
  enabled: true
  paths:
    - /var/log/auth.log
  fields:
    log_type: authlog

- type: log
  enabled: true
  paths:
    - /var/log/audit/audit.log
  fields:
    log_type: auditd-logs
```

Notes:
- Keep indentation consistent.
- Use `enabled: true`, not `enable: true`.
- Remove any stray tokens or random strings from the YAML file.
- For high-performance setups, consider `filestream`.

## 9. Configure Filebeat Output
### Direct to Elasticsearch
```yaml
output.elasticsearch:
  hosts: ["http://<ELASTICSEARCH_IP>:9200"]
  username: "elastic"
  password: "changeme"
  index: "%{[fields.log_type]}-%{+yyyy.MM.dd}"

setup.template.name: "filebeat"
setup.template.pattern: "filebeat-*"
```

### Or send to Logstash
```yaml
output.logstash:
  hosts: ["<LOGSTASH_IP>:5044"]
```

Common mistakes:
- Use `hosts`, not `host`.
- Match `http://` or `https://` correctly.
- Avoid duplicate output blocks.

## 10. Enable Modules and Dashboards
- Enable the auditd module:
  - `sudo filebeat modules enable auditd`
- Load dashboards:
  - `sudo filebeat setup --dashboards`
- Load templates and pipelines:
  - `sudo filebeat setup -e`

## 11. Start and Test Filebeat
- Restart:
  - `sudo systemctl restart filebeat`
- Check status:
  - `sudo systemctl status filebeat`
- Test output connectivity:
  - `sudo filebeat test output`
- Check logs:
  - `sudo journalctl -u filebeat -f`
- Verify indices in Elasticsearch:
  - `GET _cat/indices?v`

## 12. Kibana Data Views and Dashboards
- In Kibana: Stack Management -> Data Views -> Create a data view for `filebeat-*` or your custom index pattern.
- Use `@timestamp` as the time field.
- Use Discover to view incoming logs.
- Open dashboards after loading them.

## 13. Troubleshooting Checklist
- Filebeat not sending:
  - Run `sudo filebeat test output`
  - Check `sudo journalctl -u filebeat -f`
  - Confirm network connectivity to Elasticsearch.
- No indices in Elasticsearch:
  - Confirm `output.hosts`, username, and password.
  - Look for template or pipeline errors.
- Kibana shows errors:
  - Verify Kibana can reach Elasticsearch.
  - Check `/etc/kibana/kibana.yml`.
  - Review Kibana logs.
- Log parsing issues:
  - Use Logstash or Filebeat processors.
- YAML problems:
  - Fix indentation, stray characters, or wrong key names.

## 14. Security Best Practices
- Enable xpack security in Elasticsearch.
- Use TLS for transport and HTTP.
- Create least-privilege users for Kibana and Beats.
- Use API keys for Beats where possible.
- Protect Kibana with HTTPS and strong credentials.
- Avoid disabling security except for temporary testing.

## 15. Example Clean Filebeat Config
```yaml
filebeat.inputs:
- type: log
  enabled: true
  paths: ["/var/log/syslog"]
  fields: { log_type: syslog }

- type: log
  enabled: true
  paths: ["/var/log/auth.log"]
  fields: { log_type: authlog }

- type: log
  enabled: true
  paths: ["/var/log/audit/audit.log"]
  fields: { log_type: auditd-logs }

output.elasticsearch:
  hosts: ["http://192.168.1.4:9200"]
  username: "elastic"
  password: "changeme"
  index: "%{[fields.log_type]}-%{+yyyy.MM.dd}"

setup.template.name: "filebeat"
setup.template.pattern: "filebeat-*"
```

## 16. Useful Commands
- `systemctl status filebeat`
- `sudo filebeat test output`
- `sudo filebeat setup -e`
- `sudo filebeat modules enable auditd`
- `sudo filebeat setup --dashboards`
- `sudo /usr/share/logstash/bin/logstash --config.test_and_exit -f /etc/logstash/conf.d/`
- `curl -u elastic https://localhost:9200/`
- `curl http://localhost:9200/`
- `GET _cat/indices?v`

## Next Steps
If needed, generate:
- A ready-to-use `/etc/filebeat/filebeat.yml`
- A ready-to-use `/etc/kibana/kibana.yml`
- A sample Logstash pipeline for port 5044
- Secure user/role setup commands
