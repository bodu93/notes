对于机器级编程来说，其中两种抽象尤为重要：

* 由指令集体系结构或指令集架构(Instruction Set Architecture, ISA)来定义机器级程序的格式和行为，它定义了处理器状态、指令的格式，以及每条指令对状态的影响。
* 机器级程序使用的内存地址是虚拟地址，提供的内存模型看上去是一个非常大的字节数组(平坦寻址模式-flat addressing model)。



x86-64寄存器分类:

* 程序计数器(简称"PC"，在x86-64中用`%rip`表示）给出将要执行的下一条指令在内存中的位置。
* 整数寄存器：包含16个命名的位置，分别存储64位的值。这些寄存器可以存储地址或整数数据、程序状态、临时数据以及程序的返回值等。
* 条件码寄存器：保存最近执行的算术或逻辑指令的状态信息。
* 向量寄存器可以存放一个或多个整数或浮点数。



The best strategy is to compile the code with `-S` command-line option and then examine the generated assembly code to see if it will have the desired effect. The code should be tested with different settings of switches such as with different levels of optimizaton.