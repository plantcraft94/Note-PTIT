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

---
# Giới thiệu về CPU pipeline

| IF  | ID  | EX  | MEM | WB  |
| --- | --- | --- | --- | --- |
Cải thiện hiệu năng bằng cách tăng số lượng lện vào xử lí

| IF  | ID  | EX  | MEM | WB  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ->  | IF  | ID  | EX  | MEM | WB  |     |     |     |
| ->  |     | IF  | ID  | EX  | MEM | WB  |     |     |
| ->  |     |     | IF  | ID  | EX  | MEM | WB  |     |
| ->  |     |     |     | IF  | ID  | EX  | MEM | WB  |
Nhận xét: chia thực hiện lệnh thành 5 bước -> Hiệu quả theo Pipeline hơn tương đương 5 lần

=> Pipeline là kĩ thuật song song ở mức lện để tăng tốc độ tính toán
## Vấn đề xảy ra:
- xung đột tài nguyên (resource conflict)
	- Xung đột truy cập bộ nhớ
	- xung đột truy cập thanh ghi
	- Giải pháp:
		- Nâng cao khả năng tài nguyên
		- Memory/cache: hỗ trợ nhiều thao tác đọc/ ghi cùng lúc
		- Chia memory thành cache lệnh và cache dữ liệu để cải thiện truy nhập
- Xung đột / tranh chấp dữ liệu (data hazard)
	- Hầu hết là RAW hay Read After Write Hazard
	- Giải pháp:
		- Ngưng Pipeline (Stall): phải làm trễ hoặc nhưng pipeline bằng cách sử dụng 1 vài phương pháp tới khi có dữ liệu chính xác
		- Chèn NO-OP
		- Chèn các lệnh độc lập dữ liệu vào giữa các lệnh cần dữ liệu
			- Ví dụ:
			- 
- Các lệnh rẽ nhánh ()
Ví dụ:
ADD R1, R1, R3                        R1 <- R1+R3
SUB 

| IF  | ID  | EX    | MEM   | WB    |     |     |     |     |
| --- | --- | ----- | ----- | ----- | --- | --- | --- | --- |
| ->  | IF  | STALL | STALL | STALL | ID  | EX  | MEM | WB  |



NO-OP

| IF  | ID    | EX    | MEM   | WB    |       |       |       |     |
| --- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | --- |
| ->  | NO-OP | NO-OP | NO-OP | NO-OP | NO-OP |       |       |     |
| ->  |       | NO-OP | NO-OP | NO-OP | NO-OP | NO-OP |       |     |
| ->  |       |       | NO-OP | NO-OP | NO-OP | NO-OP | NO-OP |     |
| ->  |       |       |       | IF    | ID    | EX    | MEM   | WB  |
Chèn các lệnh độc lập dữ liệu vào giữ ADD và SUB

![[Pasted image 20260128082049.png]]