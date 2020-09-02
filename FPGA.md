# FPGA

## OPAE

### Intel PAC D5005

```bash
# .bashrc
export QUARTUS_HOME="/opt/intelFPGA_pro/quartus_19.2.0b57/quartus"
export OPAE_PLATFORM_ROOT="/opt/inteldevstack/d5005_ias_2_0_1_b237"
export AOCL_BOARD_PACKAGE_ROOT="/opt/inteldevstack/d5005_ias_2_0_1_b237/opencl/opencl_bsp"
OPAE_PLATFORM_BIN="/opt/inteldevstack/d5005_ias_2_0_1_b237/bin"
export PATH="${PATH}":"${OPAE_PLATFORM_BIN}"
export INTELFPGAOCLSDKROOT="/opt/intelFPGA_pro/quartus_19.2.0b57/hld"
export ALTERAOCLSDKROOT=$INTELFPGAOCLSDKROOT
export PAC_DMA_WORK_THREAD=yes
QUARTUS_BIN="/opt/intelFPGA_pro/quartus_19.2.0b57/quartus/bin"
export PATH="${QUARTUS_BIN}":"${PATH}"
source $INTELFPGAOCLSDKROOT/init_opencl.sh >> /dev/null
# run the below line after every reboot
#source $AOCL_BOARD_PACKAGE_ROOT/linux64/libexec/setup_permissions.sh >> /dev/null 
```

### ModelSim

```bash
# .bashrc
export MTI_HOME=/opt/intelFPGA_pro/quartus_19.2.0b57/modelsim_ase
export PATH=$MTI_HOME/bin:$PATH
```

Install 32-bit libraries.

```bash
$ sudo yum install glibc-devel.i686 libX11.i686 libXext.i686 libXft.i686 ncurses-libs.i686
```

* `vlib work`: Create a physical library (i.e., directory) `work`
* `vmap work work`: Map a logical library `work` to a physical library `work`
* `vlog counter.v test_counter.v`: Compile sources
* `vsim work.test_counter`: Start simulation
