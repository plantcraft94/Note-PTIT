# CENTRAL PROCESSING UNIT (CPU)
---
# 1. CPU Diagram
![[Pasted image 20260121075126.png]]

CU : Control Unit
IR: Instruction Register
PC: Program Counter
MAR: Memory Address Register
MBR: Memory Buffer Register
FR: Flag Register
ALU: Arithmetic and Logic Unit
A: Accumulator Register
Y, Z: Temporary Register
# 2. Instruction execution:
1. OS loads the program code into the memory;
2. Program Counter (PC) = address of the memory cell that stores the first instruction of the program
3. MAR = PC then upload to bus A
4. Bus A passes the cell address to MMU - Memory Management Unit;
5. MMU selects and reads data from cell
6. Instruction code or data (stored on the cell) is uploaded on bus D and then stored on the MBR register
7. MBR transfer the instruction code to IR (as an input for CU)
8. CU decodes the instruction code, and generates the control signals and send them to other component (such as ALU), for making the instruction be executed
9. PC is increased by 1 and points to the memory cell that is stored the next instruction to be executed
10. Repeat step 3rd - 9th for all instructions of program.
![[Pasted image 20260121081339.png]]
# 3. Registers
- Act as memory cells, registers can:
	- tempo
## Accumulator (A)
- present in most CPU, A can be used for:
	- storing the input operands
	- Storing the results
	- communicating between CPU and I/O
- Size can be varied: 8,16,32, 64 bit
## Flag Register (FR)
## Stack pointer
## General purpose Registers
# 4. Control Unit (CU)
![[Pasted image 20260121085857.png]]

# 5. Arithmetic Logic Unit (ALU)
![[Pasted image 20260121090630.png]]
# 6. Internal Bus
- a channel for communicating among units inside of CPU (CU - Registers - ALU);
- Full duplex (2-ways communicate)
- 
# 7. Example
