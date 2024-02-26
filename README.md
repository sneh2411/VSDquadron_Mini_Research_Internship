# VSDquadron_Mini_Research_Internship
A 4 week Extensive Research based Internship on VSDSquadron Mini board for RTL to Advanced Developers.
This repositary is mainly to document the learning outcomes and experience of a 4-week Industry style work culture on VLSI and RISC-V using VSDSquadron Mini RISC-V Development kit.

Received development board on 14th February 2024 at 12.45pm.

## VSDquadron_Mini

  
  ![VSDS_Mini](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/2c37b17f-4247-4a84-a2e1-1d5724a26c49)

  ### DataSheet 

 The datasheet of VSDSQuadron Mini is as showm as (https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/files/14395714/VSDSQMinidatasheet.pdf)


The first online meeting was conducted on 16th February, 2024, @ 6PM to 7PM

#### TASK 1: Deadline 20th Feb 2024

1. Create GitHub repo. 
2. Need to have Windows OS, 1TB HDD, 16GB RAM.
3. Allocate 8GB RAM, 100GB HDD for Oracle Virtual Machine 
4. install RISC-V GNU Toolchain first, then install Yosys, iverilog, gtkwave. 
5. Refer to this course :VSD - A complete guide to install open-source EDA tools to install Ubuntu 20.04 using Virtual Box


##### Installation of RISC V GNU Tool Chain
+ sudo apt install git-all   # To install git and all related packages.
- sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev
* git clone https://github.com/riscv/riscv-gnu-toolchain --recursive
* mkdir riscv   # in home directory
+ chmod -R 777 /home/extcelxlab/riscv
- ./configure --prefix=/home/extcelxlab/riscv
![RISCV](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/db85b633-59cd-4c0c-a287-77d87586cd43)


Also, do run below commands for installing build-essentials and avoiding error in gcc installation
-  sudo apt-get install build-essential
 Add gcc path in $PATH variable or add in .bashrc file(in home directory), add at last line
+  gvim .bashrc
*   export PATH= "$PATH:/usr/bin/gcc"

##### Installation of Yosys

![yosys_commands](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/5a795fd4-a264-4139-a32e-f2c34ed8fd0c)


![Yosys](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/f5fb406d-6d11-4506-bd7d-da84f4d0009a)

![Yosys_build](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/fc93dd8c-8e8f-47fd-bb76-88106cefe6a4)

##### Installation of iverilog




##### Installation of gtkwave



#### TASK 2: Understand the instruction set in detail     Deadline on 22nd February 2024
RISC V instructions are each of 32 bits or 4 bytes

![32bit RISCV IS](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/a7873ec1-9282-4294-96bd-1168d31eb1f5)


![RISC V Instruction set](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/99e4278e-5b3d-4b94-84de-33eea7b33c35)

These are divided into fields.
There are 6 instruction formats 
1. Register type formats : This uses 3 register inputs Eg : add, mul, AND - All are basically arithmetic and logical operations
 Eg: add r6,r2,r1   r1 and r2 are source registers and r6 is destination register
2: I-type: immediate and load operations 
Eg: addi r12,r4,5
    lw x14,x2,8
3. S-type: store operations 
Eg: sw x12, x2,8
4. B-type: conditional branch operations 
Eg: beq r0, r0 ,15
    bne r0, r1,20
5. U-type: long immediate operation
#### TASK 3: Execution of C Based Lab and RISC V based Lab   Deadline on 27th February 2024
1. Compiling C Code

![CProgram](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/e9b370ea-38a1-4df5-abfc-92ea712399ce)

2. Compiling C code using RISC-V gcc complier

   riscv64-unknown-elf-gcc -o1 -o sum1ton.o sum1ton.c
   
4.  After compiling, we can see assembply code generated using RISC-V Objdmp as below
   riscv64-unknown-elf-objdump -d fact8.o | less

