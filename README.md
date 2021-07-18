# VLSI system design low power workshop

# Installing the ngspice using brew do not open up gui (brew install ngspice). Following steps, I have followed while installing in Mac M1
* git clone git://git.code.sf.net/p/ngspice/ngspice
* zsh ./compile_macos.sh
  * release/src/ngspice is the binary path to be used
  * open ~/.zshrc and update the installing path

# Installing open source skywater 130nm pdk from google github page
1. git clone https://github.com/google/skywater-pdk
2. cd skywater-pdk
3. git submodule init libraries/sky130_fd_io/latest
4. git submodule init libraries/sky130_fd_pr/latest
5. git submodule init libraries/sky130_fd_sc_hd/latest
6. git submodule init libraries/sky130_fd_sc_hvl/latest
7. git submodule init libraries/sky130_fd_sc_hdll/latest
8. git submodule init libraries/sky130_fd_sc_hs/latest
9. git submodule init libraries/sky130_fd_sc_ms/latest
10. git submodule init libraries/sky130_fd_sc_ls/latest
11. git submodule init libraries/sky130_fd_sc_lp/latest
12. git submodule update
13. make timing

# Install magic tool, clone and follow the instructions in readme
1. git clone https://github.com/RTimothyEdwards/magic
2. ./configure
3. make
4. make install

# you can try installing using ports
sudo port install magic
 
# Once skywater pdk is installed, install open_pdks from Timothy Edwards github repo
1. git clone https://github.com/RTimothyEdwards/open_pdks
1. cd open_pdks
1. ./configure --enable-sky130-pdk=~/workspaces/pdk/skywater-pdk/libraries --with-sky130-local-path=~/workspaces/pdks
1. make -j4
1. make install

5G has multiple converge points.
IOT
Edge computing, Edge networking is a distributed computing paradigm that brings computation and data storage as close to the point of request (some where near to towers itself) as possible in order to deliver low latency and save bandwidth.
Beyond iOS or Android, we are over due for the next level of platform 

Which place to implement Low-power to have higher impact?
* Architecture/Software > Algorithm > RTL > Physical Design
  * RTL : Datagating, clockgating,  xor gating and all other techniques are automatically done by synthesis tools even though user has written a bad RTL code
  * PD : multi-VT opt, multibit combo/sequential cell optimization, clock gating cloning and merging
