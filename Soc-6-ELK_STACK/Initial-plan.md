# Installation

## Options:

| Option | Description                         | Host RAM Needed (Practical) | VM/Container RAM   | Performance on 8 GB Host | Difficulty  | Recommended for You |
| ------ | ----------------------------------- | --------------------------- | ------------------ | ------------------------ | ----------- | ------------------- |
| **1**  | Manual ELK on Ubuntu Server VM      | 8 GB host minimum           | 4 GB VM            | ✅ Good if optimized      | Medium      | ⭐ Best              |
| **2**  | Install ELK directly on Ubuntu host | 8 GB host                   | No VM overhead     | ✅ Better performance     | Medium      | ⭐ Very Good         |
| **3**  | Docker ELK                          | 8–12 GB host preferred      | ~4–6 GB containers | ⚠️ Can lag               | Easy–Medium | Good                |
| **4**  | Bitnami ELK VM / OVA                | 12 GB+ preferred            | 6–8 GB VM          | ❌ Heavy on 8 GB          | Easy        | Not ideal           |
| **5**  | Minimal / Simulated setup           | 4–8 GB host                 | 2–4 GB             | ✅ Smooth                 | Easy        | Backup option       |




# Ubuntu has two common editions:

| Edition        | Has GUI/Desktop? | RAM Usage |
| -------------- | ---------------- | --------- |
| Ubuntu Server  | ❌ No             | Low       |
| Ubuntu Desktop | ✅ Yes            | Higher    |



Elasticsearch, Logstash, Kibana

# Download Files
1. Ubuntu Server LTS ISO - (24.04 LTS, 22.04 LTS) 64bit
2. Elasticsearch
3. Kibana
4. Logstash

# Optional Components (NOT required for your assignment)
| Component  | Purpose                              |
| ---------- | ------------------------------------ |
| Filebeat   | Sends logs to Logstash/Elasticsearch |
| Metricbeat | CPU/RAM monitoring                   |
| Packetbeat | Network traffic metadata             |
| Winlogbeat | Windows Event Logs                   |



# installation 


