# 🚀 Week 0 – Tools Installation

## 📌 Overview
Week 0 is all about preparing the environment for the SoC Labs journey.  
The focus is on setting up open-source EDA tools that will be used throughout the program for **design, simulation, synthesis, and layout**.

---

## 🖥️ Environment Setup
- I am using **VirtualBox with Ubuntu 20.04 LTS**.  
- Alternatives include:  
  - **WSL (Windows Subsystem for Linux)** → Ubuntu on Windows  
  - **Dedicated Ubuntu OS** → Native installation for better performance  

### 🔧 System Requirements
| Resource | Requirement |
|----------|-------------|
| OS       | Ubuntu 20.04+ |
| CPU      | 4 vCPUs |
| RAM      | 6 GB minimum |
| Storage  | 50 GB HDD |

---

## 🛠️ Tools Installed

| Tool        | Purpose / Why It’s Used | Verification Command | Screenshot |
|-------------|--------------------------|----------------------|-------------|
| **Yosys**   | Open-source framework for **logic synthesis** (RTL → gate-level netlist). | `yosys -V` | ![yosys](./screenshots/yosys.png) |
| **Icarus Verilog** | A **Verilog simulator** used to test RTL designs and verify functionality. | `iverilog -V` | ![iverilog](./screenshots/iverilog.png) |
| **GTKWave** | **Waveform viewer** for analyzing simulation results (`.vcd` files). | `gtkwave --version` | ![gtkwave](./screenshots/gtkwave.png) |
| **Ngspice** | **Analog and mixed-signal circuit simulation** at SPICE-level. | `ngspice -v` | ![ngspice](./screenshots/ngspice.png) |
| **Magic**   | **VLSI layout editor** for viewing and editing layouts. | `magic -version` | ![magic](./screenshots/magic.png) |
| **OpenLANE** | Complete **RTL-to-GDSII flow** (synthesis, placement, routing, signoff). | `docker --version` <br> `make test` | ![openlane](./screenshots/openlane.png) |

---
## ⚙️ Week 0 – Installation Commands
This section contains all installation steps for the tools required in Week 0. 
### * System Update
`
$sudo apt-get update 
$sudo apt-get upgrade 
`

## 1. Yosys
`
sudo apt-get update
git clone https://github.com/YosysHQ/yosys.git
cd yosys
sudo apt install make   # if not already installed
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
make config-gcc
make
sudo make install
`

## 2. Icarus Verilog
`
sudo apt-get install iverilog
`

## 3. GTKWaves
`
sudo apt install gtkwave
`

## 4. Ngspice
`
Download ngspice tarball from: https://sourceforge.net/projects/ngspice/files/
tar -zxvf ngspice-37.tar.gz  # change as per the version you download
cd ngspice-37
mkdir release
cd release
../configure --with-x --with-readline=yes --disable-debug
make
sudo make install
`

## 5. Magic
`
sudo apt-get install m4
sudo apt-get install tcsh
sudo apt-get install csh
sudo apt-get install libx11-dev
sudo apt-get install tcl-dev tk-dev
sudo apt-get install libcairo2-dev
sudo apt-get install mesa-common-dev libglu1-mesa-dev
sudo apt-get install libncurses-dev
git clone https://github.com/RTimothyEdwards/magic
cd magic
./configure
make
make install
`
## 6.OpenLANE
`
sudo apt-get update
sudo apt-get upgrade
sudo apt install -y build-essential python3 python3-venv python3-pip make git
sudo apt install apt-transport-https ca-certificates curl software-properties-common
**Install Docker**
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
**Verify Docker**
sudo docker run hello-world
**Add user to docker group**
sudo groupadd docker
sudo usermod -aG docker $USER
sudo reboot
**After reboot**
docker run hello-world
**Check dependencies**
git --version
docker --version
python3 --version
python3 -m pip --version
make --version
python3 -m venv -h
**Install PDKs and tools**
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
`


---

