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

---

