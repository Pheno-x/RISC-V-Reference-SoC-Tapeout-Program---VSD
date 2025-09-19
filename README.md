# RISC-V Reference SoC Tapeout Program -- VSD
![RISC-V](https://img.shields.io/badge/RISC--V-Processor-blue?logo=risc-v&logoColor=white)
![SOC Tapeout](https://img.shields.io/badge/SoC-Tapeout-blue)
![VSD Program](https://img.shields.io/badge/VSD-Program-orange)
![Made in India](https://img.shields.io/badge/Made%20in-India-green?logo=india&logoColor=white)

## My SoC Labs Journey 🚀
> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  
> 🚀 ***From Design to Silicon with Industry-Grade Tools*** 🔧  
> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━




This repo is not just code and screenshots — it’s a record of my journey through the **VSD SoC Labs Program**.  
I’m starting from the very beginning, with no shortcuts. Every week, I’ll document what I learn, what I build, and even the mistakes I make along the way. 

I’m documenting this so future learners (and my future self) can see the growth from day 0 to the final tapeout.

# Week 0 – Tools Installation 🛠️

| Tool        | Installation Command(s) | Verification Command | Screenshot |
|-------------|--------------------------|----------------------|-------------|
| **Yosys**   | `git clone https://github.com/YosysHQ/yosys.git` <br> `make config-gcc && make && sudo make install` | `yosys -V` | ![yosys](./screenshots/yosys.png) |
| **Icarus Verilog** | `sudo apt-get install iverilog` | `iverilog -V` | ![iverilog](./screenshots/iverilog.png) |
| **GTKWave** | `sudo apt install gtkwave` | `gtkwave --version` | ![gtkwave](./screenshots/gtkwave.png) |
| **Ngspice** | `../configure --with-x --with-readline=yes --disable-debug` <br> `make && sudo make install` | `ngspice -v` | ![ngspice](./screenshots/ngspice.png) |
| **Magic**   | `git clone https://github.com/RTimothyEdwards/magic` <br> `./configure && make && make install` | `magic -version` | ![magic](./screenshots/magic.png) |
| **OpenLANE** | `git clone https://github.com/The-OpenROAD-Project/OpenLane` <br> `make && make test` | `docker --version` <br> `make test` | ![openlane](./screenshots/openlane.png) |
