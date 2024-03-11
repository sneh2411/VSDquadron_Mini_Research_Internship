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

   riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c  ( The number of instruction get reduced)
   
   ![task3riscv1](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/321f95e4-7717-434b-9eb0-ffe2eb9c4468)

4.  After compiling, we can see disassembply code generated using RISC-V Objdmp as below

 riscv64-unknown-elf-objdump -d sum1ton.o | less

![task3dump1](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/7fc41f45-664d-4275-a811-656d983ef96c)
#### TASK 4: Execution of GCC and SPIKE Based RISC V GCC   Deadline on 29th February 2024
SPIKE Simulation and observation with -O1 and -Ofast. 
Upload snapshot of compiled C Code, RISC-V Objdmp with above options on your GitHub repo
1. Sorting program is written in VI editor as shown below
   ![t1](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/898bbb3d-ca4d-4702-8714-6dcd44354a6f)

2. Output of C code (GCC ) is as follows:
   ![t2](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/77435bdd-d80a-45a3-b0b0-d08470018a4e)

3. ![t3](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/8f024994-56a0-4753-83b7-2fe8a67e7468)
4. ![t4](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/5cd19937-2b6f-440d-8590-69e36d4f3b8f)
Spike simulator not able to install  in vdi. Error is as shown below
5. The spike simulator did not work in virtual Image. Need to trouble shoot error for the same.
6.
![t5](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/dcbfdd09-f2dc-4e19-9a45-7481b7d26eed)
  
#### TASK 5: Execution of  given RISCV Verilog Netlists and Testbench for functional Simulation   Deadline on 5th March 2024
Before starting this experiment, we are required to install iverlog and gtkwave software. The commands to run the experiment is as follows:
1. ![Task5_1](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/ddc83b4d-bdc8-4f53-81b0-bd2b1598ff2f)
Once gtkwave command is given, we get the following:
3. ![add_4](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/6fe9a5f0-75b7-4d73-b9e7-19e4eef5e2de)
4. ![Task5_3](https://github.com/sneh2411/VSDquadron_Mini_Research_Internship/assets/46631767/7dcd68db-2dab-438e-83d0-5ae3f5b7b14e)
#### Final Task as of 7th March, 2024 is GLS for your design and final documentation (Deadline is 14th March)
Now synthesis is to be done
