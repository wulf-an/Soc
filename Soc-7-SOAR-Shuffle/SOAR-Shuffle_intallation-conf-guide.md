# Installation methods

1. Docker Engine comes bundled with Docker Desktop for Linux. This is the easiest and quickest way to get started.

2. Set up and install Docker Engine from Docker's apt repository.

3. Install it manually and manage upgrades manually.

4. Use a convenience script. Only recommended for testing and development environments.


# Install using the apt repository
--------------------------------------------------------------------------
# 1. Set up Docker's apt repository.
--------------------------------------------------------------------------
# Add Docker's official GPG key:
- sudo apt update
- sudo apt install ca-certificates curl
- sudo install -m 0755 -d /etc/apt/keyrings  - Creates a new folder specifically for storing security keys.
- sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
- sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update

* check it : apt-cache policy docker-ce

------------------------------------------------------------------------
# 2. Install the Docker packages.
------------------------------------------------------------------------

- To install the latest version, run:

sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

- After installation, verify that Docker is running:
sudo systemctl status docker
sudo systemctl start docker


--------------------------------------------------------------------------
# 3. Verify that the installation is successful by running the hello-world image:
--------------------------------------------------------------------------

sudo docker run hello-world

This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits.


-------------------------------------------------------------------------
# 4. Clone the Shuffle Repository & Prepare Directories
-------------------------------------------------------------------------

# 1. Install git if you don't already have it
sudo apt update && sudo apt install git -y

# 2. Clone the official repository and enter the directory
git clone https://github.com/Shuffle/Shuffle.git
cd Shuffle

# 3. Create a folder for the database
mkdir shuffle-database

# 4. Give the internal database container user (ID 1000) ownership of this folder
sudo chown -R 1000:1000 shuffle-database
