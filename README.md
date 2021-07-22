# MIPS-Microprocessor

# [Electronics Club IITG Project](https://www.iitg.ac.in/stud/gymkhana/technical/home/ElectronicsHome.html)

# Overview
- A Verilog-based project. A 16 - bit single-cycle MIPS Processor is implemented in Verilog HDL.
- The Microprocessor does one of the six instructions (Add, Add immediately, Load Word, Store Word, Branch Equals, Jump) in a cycle.
- First, the datapaths are constructed. And then, they are combined into a single datapath. 
- And then the control is added. And then the control is set to every instruction.
# Datapaths
- The datapaths contain all the hardware required to implement one of these instructions.
- For the add instruction: 
        Each time through the loop, a different add instruction is pulled, and then two source registers are selected and data is requested.
        And the source register is selected. Then the source values go to ALU, where they will be added and then they will be stored back in the destination register.
        And the program counter is incremented.
- For the add immediate instruction:
        Each time through the loop, a specific add immediate instruction is pulled, then the source register is picked along with the immediate. And then they are added together and then the data is stored back in registers. And the program counter is incremented.
- For the load word instruction:
        Each time through the loop, a base address and an offset are pulled, then passed to ALU, and then the target address is calculated. It is then used to fetch the data from registers, which is then stored back in the selected register. And then 4 is added to the program counter. 
- For the store word instruction:
        Each time through the loop, the instruction is pulled. Which tells what the base address and offset is, and the data that needs to be stored. The ALU adds the base address and offset, which gives the destination address. And then the data is stored in the destination register. And then the program counter is incremented.
- For the branch equals instruction: 
        Each time through the loop, the instruction is pulled, then the data from the two registers is obtained and then based on whether the data is equal or not, the target instruction or the next instruction is selected. The branch target instruction is calculated by adding the current address and the offset that was directly obtained from the branch instruction. And the program counter is incremented.
- For the jump instruction: 
        Each time through the loop, the instruction is pulled, which gives the address of the next instruction, which is passed to the program counter. And then the program counter is incremented.
