# 功能测试

功能测试程序集为 MIPS 汇编程序，用于测试 CPU 功能并在实验箱上显示。当CPU从内存中执行测试程序后，实验箱上的数码管和 LED 灯显示分数和测试通过情况。文档介绍了功能测试的使用方法和功能测试程序和环境。

## 功能测试程序

本小节介绍功能测试程序包含的内容，可以结合测试程序阅读。
功能测试的主程序位于 src/start.S，src/inst 目录下为测试 文件 `n1_add.S` \~ `n93_tlbwr.S`，每个测试文件对应一个功能测试点。功能测试程序集包含的功能测试点如下:

| 序号 | Hex | 测试程序 | 功能测试点|
|:--- | :--- |:--- |:--- |
| 1 | 0x01| ADD | 执行 ADD 指令是否产生正确的运算结果（未测试整型溢出例外的情况） |
| 2 | 0x02|ADDI | 执行 ADDI 指令是否产生正确的运算结果（未测试整型溢出例外的情况） |
| 3 | 0x03|ADDU | 执行 ADDU 指令是否产生正确的运算结果 |
| 4 | 0x04|ADDIU | 执行 ADDIU 指令是否产生正确的运算结果 |
| 5 | 0x05| SUB | 执行 SUB 指令是否产生正确的运算结果（未测试整型溢出例外的情况） |
| 6 | 0x06| SUBU | 执行 SUBU 指令是否产生正确的运算结果 |
| 7 | 0x07| SLT | 执行 SLT 指令是否产生正确的运算结果 |
| 8 | 0x08| SLTI | 执行 SLTI 指令是否产生正确的运算结果 |
| 9 | 0x09| SLTU | 执行 SLTU 指令是否产生正确的运算结果 |
| 10 | 0x0a| SLTIU | 执行 SLTIU 指令是否产生正确的运算结果 |
| 11 | 0x0b| DIV | 执行 DIV 指令是否产生正确的运算结果 |
| 12 | 0x0c| DIVU | 执行 DIVU 指令是否产生正确的运算结果 |
| 13 | 0x0d| MULT | 执行 MULT 指令是否产生正确的运算结果 |
| 14 | 0x0e| MULTU | 执行 MULTU 指令是否产生正确的运算结果 |
| 15 | 0x0f| AND | 执行 AND 指令是否产生正确的运算结果 |
| 16 | 0x10| ANDI | 执行 ANDI 指令是否产生正确的运算结果 |
| 17 | 0x11| LUI | 执行 LUI 指令是否产生正确的运算结果 |
| 18 | 0x12| NOR | 执行 NOR 指令是否产生正确的运算结果 |
| 19 | 0x13| OR | 执行 OR 指令是否产生正确的运算结果 |
| 20 | 0x14| ORI | 执行 ORI 指令是否产生正确的运算结果 |
| 21 | 0x15| XOR | 执行 XOR 指令是否产生正确的运算结果 |
| 22 | 0x16| XORI | 执行 XORI 指令是否产生正确的运算结果 |
| 23 | 0x17| SLLV | 执行 SLLV 指令是否产生正确的移位结果 |
| 24 | 0x18| SLL | 执行 SLL 指令是否产生正确的移位结果 |
| 25 | 0x19| SRAV | 执行 SRAV 指令是否产生正确的移位结果 |
| 26 | 0x1a| SRA | 执行 SRA 指令是否产生正确的移位结果 |
| 27 | 0x1b| SRLV | 执行 SRLV 指令是否产生正确的移位结果 |
| 28 | 0x1c| SRL | 执行 SRL 指令是否产生正确的移位结果 |
| 29 | 0x1d| BEQ | 执行 BEQ 指令是否产生正确的判断和跳转结果（延迟槽指令为nop，未测试延迟槽） |
| 30 | 0x1e| BNE | 执行 BNE 指令是否产生正确的判断和跳转结果（延迟槽指令为nop，未测试延迟槽） |
| 31 | 0x1f| BGEZ | 执行 BGEZ 指令是否产生正确的判断和跳转结果（延迟槽指令为 nop，未测试延迟槽） |
| 32 | 0x20| BGTZ | 执行 BGTZ 指令是否产生正确的判断和跳转结果（延迟槽指令为 nop，未测试延迟槽） |
| 33 | 0x21| BLEZ | 执行 BLEZ 指令是否产生正确的判断和跳转结果（延迟槽指令为 nop，未测试延迟槽） |
| 34 | 0x22| BLTZ | 执行 BLTZ 指令是否产生正确的判断和跳转结果（延迟槽指令为 nop，未测试延迟槽） |
| 35 | 0x23| BGEZAL | 执行 BGEZAL 指令是否产生正确的判断、跳转和链接结果（延迟槽指令为 nop，未测试延迟槽） |
| 36 | 0x24| BLTZAL | 执行 BLTZAL 指令是否产生正确的判断、跳转和链接结果（延迟槽指令为 nop，未测试延迟槽） |
| 37 | 0x25| J | 执行 J 指令是否产生正确的跳转结果（延迟槽指令为 nop，未测试延迟槽） |
| 38 | 0x26| JAL | 执行 JAL 指令是否产生正确的跳转和链接结果（延迟槽指令为nop，未测试延迟槽） |
| 39 | 0x27| JR | 执行 JR 指令是否产生正确的跳转结果（延迟槽指令为 nop，未测试延迟槽） |
| 40 | 0x28| JALR | 执行 JALR 指令是否产生正确的跳转和链接结果（延迟槽指令为 nop，未测试延迟槽） |
| 41 | 0x29| MFHI | 执行 MTHI 指令是否正确地将寄存器值写入 HI 寄存器，执行MFHI 指令是否正确地读出 HI 寄存器的值到寄存器 |
| 42 | 0x2a| MFLO | 执行 MTLO 指令是否正确地将寄存器值写入 LO 寄存器，执行MFLO 指令是否正确地读出 LO 寄存器的值到寄存器 |
| 43 | 0x2b| MTHI | 执行 MTHI 指令是否正确地将寄存器值写入 HI 寄存器，执行MFHI 指令是否正确地读出 HI 寄存器的值到寄存器 |
| 44 | 0x2c| MTLO | 执行 MTLO 指令是否正确地将寄存器值写入 HI 寄存器，执行MFLO 指令是否正确地读出 HI 寄存器的值到寄存器 |
| 45 | 0x2d| BREAK | 执行 BREAK 指令是否正确地产生断点例外 |
| 46 | 0x2e| SYSCALL | 执行 SYSCALL 指令是否正确地产生系统调用例外 |
| 47 | 0x2f| LB | 结合 SW 指令，执行 LB 指令是否产生正确的访存结果 |
| 48 | 0x30| LBU | 结合 SW 指令，执行 LBU 指令是否产生正确的访存结果 |
| 49 | 0x31| LH | 结合 SW 指令，执行 LH 指令是否产生正确的访存结果 |
| 50 | 0x32| LHU | 结合 SW 指令，执行 LHU 指令是否产生正确的访存结果 |
| 51 | 0x33| LW | 结合 SW 指令，执行 LW 指令是否产生正确的访存结果 |
| 52 | 0x34| SB | 结合 LW 指令，执行 SB 指令是否产生正确的访存结果 |
| 53 | 0x35| SH | 结合 LW 指令，执行 SH 指令是否产生正确的访存结果 |
| 54 | 0x36| SW | 结合 LW 指令，执行 SW 指令是否产生正确的访存结果 |
| 55 | 0x37| ERET | 执行 ERET 指令是否正确地从中断、例外处理程序返回 |
| 56 | 0x38| MFC0 | 执行 MTC0 指令是否正确地将寄存器值写入目的 CP0 寄存器，执行 MFC0 指令是否正确地读出源 CP0 寄存器的值到寄存器 |
| 57 | 0x39| MTC0 | 执行 MTC0 指令是否正确地将寄存器值写入目的 CP0 寄存器，执行 MFC0 指令是否正确地读出源 CP0 寄存器的值到寄存器 |
| 58 | 0x3a| ADD\_EX | 测试 ADD 指令整型溢出例外 |
| 59 | 0x3b| ADDI\_EX | 测试 ADDI 指令整型溢出例外 |
| 60 | 0x3c| SUB\_EX | 测试 SUB 指令整型溢出例外 |
| 61 | 0x3d| LH\_EX | 测试 LH 指令访存地址非对齐例外 |
| 62 | 0x3e| LHU\_EX | 测试 LHU 指令访存地址非对齐例外 |
| 63 | 0x3f| LW\_EX | 测试 LW 指令访存地址非对齐例外 |
| 64 | 0x40| SH\_EX | 测试 SH 指令访存地址非对齐例外 |
| 65 | 0x41| SW\_EX | 测试 SW 指令访存地址非对齐例外 |
| 66 | 0x42| ERET\_EX | 测试取指地址非对齐例外 |
| 67 | 0x43| RESERVED\_INSTRUCTION\_EX | 测试保留指令例外 |
| 68 | 0x44| BEQ\_DS | 测试延迟槽 |
| 69 | 0x45| BNE\_DS | 测试延迟槽 |
| 70 | 0x46| BGEZ\_DS | 测试延迟槽 |
| 71 | 0x47| BGTZ\_DS | 测试延迟槽 |
| 72 | 0x48| BLEZ\_DS | 测试延迟槽 |
| 73 | 0x49| BLTZ\_DS | 测试延迟槽 |
| 74 | 0x4a| BGEZAL\_DS | 测试延迟槽 |
| 75 | 0x4b| BLTZAL\_DS | 测试延迟槽 |
| 76 | 0x4c| J\_DS | 测试延迟槽 |
| 77 | 0x4d| JAL\_DS | 测试延迟槽 |
| 78 | 0x4e| JR\_DS | 测试延迟槽 |
| 79 | 0x4f| JALR\_DS | 测试延迟槽 |
| 80 | 0x50| BEQ\_EX\_DS | 测试延迟槽例外 |
| 81 | 0x51| BNE\_EX\_DS | 测试延迟槽例外 |
| 82 | 0x52| BGEZ\_EX\_DS | 测试延迟槽例外 |
| 83 | 0x53| BGTZ\_EX\_DS | 测试延迟槽例外 |
| 84 | 0x54| BLEZ\_EX\_DS | 测试延迟槽例外 |
| 85 | 0x55| BLTZ\_EX\_DS | 测试延迟槽例外 |
| 86 | 0x56| BGEZAL\_EX\_DS | 测试延迟槽例外 |
| 87 | 0x57| BLTZAL\_EX\_DS | 测试延迟槽例外 |
| 88 | 0x58| J\_EX\_DS | 测试延迟槽例外 |
| 89 | 0x59| JAL\_EX\_DS | 测试延迟槽例外 |
| 90 | 0x5a| JR\_EX\_DS | 测试延迟槽例外 |
| 91 | 0x5b| JALR\_EX\_DS | 测试延迟槽例外 |
| 92 | 0x5c| TLBWI | 测试TLBWI指令 |
| 93 | 0x5d| TLBWR | 测试TLBWR指令 |

功能测试大部分为随机测试，随机数预先生成并写入程序中。

功能测试采用宏指令，定义宏指令的头文件位于 src/include 下，分为 6 个文件：

- inst\_def.h 定义了第 1\~54 功能测试点的指令宏定义；(第 55\~57 功能测试点不采用宏定义)
- inst\_test.h 定义了第 1\~54 功能测试点的测试指令宏定义；(第 55\~57 功能测试点不采用宏定义)
- inst\_ex\_def.h 定义了第 58\~67 功能测试点的指令宏定义；
- inst\_ex\_test.h 定义了第 58\~67 功能测试点的测试指令宏定义；
- inst\_delay\_slot\_def.h 定义了第 68\~91 功能测试点的指令宏定义；
- inst\_delay\_slot\_test.h 定义了第 68\~91 功能测试点的测试指令宏定义。

例如第 1 个功能测试点 ADD，在功能测试主程序 start.S 中 jal 指令调用 n1\_add\_test：  

	src/start.S
	+++++++++++
	…
	inst_test:
	    jal n1_add_test #add
	    nop
	…

n1\_add\_test 功能测试子程序如下：  

	src/inst/n1_add.S
	+++++++++++++++++
	9   LEAF(n1_add_test)
	10    lui a0, 0x100
	11    li v0, 0x0
	12  ###test inst
	13    TEST_ADD(0x0480ff04, 0x40933204, 0x45143108)
	14    TEST_ADD(0x2a19dd40, 0xa87971e0, 0xd2934f20)
	…
	211   TEST_ADD(0x25e5fad8, 0x00000000, 0x25e5fad8)
	212   TEST_ADD(0x00000000, 0xdcaf5e62, 0xdcaf5e62)
	…
	262   TEST_ADD(0x00000000, 0x00000000, 0x00000000)
	263 ###detect exception
	264   bne v0, zero, inst_error
	265   nop
	266 ###score ++
	267   addiu s3, s3, 1
	268 ###output a0|s3
	269 inst_error:
	270   or t0, a0, s3
	271   sw t0, 0(s1)
	272   jr ra
	273   nop
	274 END(n1_add_test)
	
其中，第 10 行 a0 寄存器存储了测试功能点编号值，这里为 0x1；第 11 行 v0 寄存器存储的是例外检
测，初始值为 0，如果程序出现例外会置为 0xffff0000，在 264 行检测如果出现例外就会跳转到
inst\_error；第 12 行到第 262 行为测试指令，TEST\_ADD(加数 1，加数 2，正确结果)，分别测试了加数 1 和
2 都是随机数、加数 1 或 2 是 0、加数 1 和 2 都是 0 的情况；第 263~265 行判断测试过程中是否出现例外，
正确情况下没有例外；第 266~267 行，s3 寄存器存测试分值，测试通过一个功能点加 1 分；第 268~273 行
为测试结束，将测试编号和测试分值输出显示并返回主程序。

宏定义 TEST\_ADD 位于 inst\_test.h 中： 

	src/include/inst_test.h
	+++++++++++++++++++++++
	4 /* 1
	5 * TEST_ADD(vs, vt, vd)
	6 */
	7 #define TEST_ADD(vs, vt, vd) \
	8   ADD(vs, vt); \
	9   li s2, vd; \
	10  bne s0, s2, inst_error; \
	11  nop

TEST\_ADD 将加数 1 和加数 2 传给 ADD(vs, vt)，并判断目的寄存器 s0 的值是否与正确结果 s2 寄存器的值一致。ADD 宏定义位于 inst\_def.h：  

	src/include/inst_def.h
	++++++++++++++++++++++
	3 /* 1
	4 * ADD(v0, v1)
	5 */
	6 #define ADD(v0, v1) \
	7   li t0, v0; \
	8   li t1, v1; \
	9   add s0, t0, t1
	
	
ADD 将加数 1 装载于寄存器 t0，加数 2 装载于寄存器 t1，结果位于寄存器 s0。

功能测试时，测试程序存储在内存中。具体存放在物理地址段 0x00000000\~0x00200000（对应虚拟地址 0x80000000\~0x80200000）范围内。程序的入口虚地址为0x80000000。

程序需要控制板上的数码管和LED显示，其控制寄存器的地址由 src/start.S 文件中的`LED_ADDR`和`NUM_ADDR`宏定义。

## 编译和链接

本小节介绍功能测试程序编译和链接环境，作为功能测试调试时的选读内容，可以结合代码阅读。

编译和链接环境位于 src/ 目录下，其中：
bin.lds 为链接脚本，bin.lds.S 为其源码；
convert 将编译生成的二进制可执行文件转换成存储器 RAM 的初始化配置文件，convert.c 为其源码；

Makefile 和 rules.make 规定了编译的配置信息和规则，交叉编译最终生成可执行文件为 main.bin。Makefile 中需要设置交叉编译器命令前缀参数`CROSS_COMPILE`，修改该参数可直接修改 Makefile 文件或者在 make 命令行中传入。Makefile 对于硬件运行和仿真运行有分别对应的版本，区别在于硬件运行的版本每条测例后面有等待，以便人观察结果。

默认版本是在硬件运行，编译命令为`make`或`make ver=test_hw`，清理命令为`make clean`或`make clean ver=test_hw`

仿真版本的编译命令为`make ver=sim`，清理命令为`make clean ver=sim`。必须加上版本的定义，否则就按照默认版本生成或清除对应的文件。
