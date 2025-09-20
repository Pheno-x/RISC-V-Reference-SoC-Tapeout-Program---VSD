# 🏗️ OpenLane – Complete Setup Guide (Ubuntu)

This repository documents the **end-to-end installation of OpenLane** on Ubuntu using **Docker** and required dependencies.  
The focus is on making the setup **simple, repeatable, and robust** for anyone starting with RTL → GDSII flows.

---

## 🔑 Requirements

Before installation, make sure these are available:

- **Ubuntu 20.04+**  
- **Git** (for cloning repositories)  
- **Docker** (container runtime)  
- **Make** (automation tool)  
- **Python 3 + pip** (for OpenLane scripts)  

Check your system with:

~~~
git --version
docker --version
make --version
python3 --version
python3 -m pip --version
~~~

## ⚙️ Step 1: System Prep
~~~
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential curl python3 python3-pip python3-venv \
    apt-transport-https ca-certificates software-properties-common \
    gnupg lsb-release git make
~~~

## 🐳 Step 2: Install Docker
```bash
# Add Docker GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /usr/share/keyrings/docker.gpg

# Add repo
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker.gpg] \
    https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io \
    docker-compose-plugin docker-buildx-plugin

# Test
sudo docker run hello-world

# Allow non-root usage
sudo groupadd docker || true
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world
```

Docker Verification
![docker](./OutputImage/docker.jpg)

---
## 🔧 Step 3: Install OpenLane
```bash
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
```
## 🧪 Step 4: Verify Setup
```bash
make test
```
✅ Expected: OpenLane should run a sample flow and finish without errors, producing synthesis, floorplan, placement, and routing outputs.
