# 计算机体系结构第二章整理

> C2：5-10分左右， 简答题：考五级流水的图（阐述五级流水架构及功能）

这里想把每一个PPT的知识点都过一下，最好不要漏。（虽然感觉最多考的就是那个五级流水）

- Computer Design的三个ASPECT
  - architecture：指令级，用户怎么去使用
  - implementation：这个CPU（微架构）是怎么构成的
  - physical design：在芯片上如何实现

- ISA：定义了数据流和控制流

  - 比如定义了怎么存数据（内存寻址）以及怎么算数据（各种算数指令）
  - 定义了指令的格式和语义，且对于同一个ISA会有多种CPU的implementation

- CISC：复杂指令集计算机(e.g. x86)

  - 编译器友好
  - (stack-oriented)用栈来传参，节省程序计数器（显式的Push Pop指令）
  - 寄存器-内存架构：计算指令可以直接访问内存
  - 用condition code作为运算和逻辑指令的side effect

- RISC：简单指令集计算机(e.g. MIPS)

  - 更少更简单的指令
  - (register-oriented)拥有更多的寄存器来传参
  - 只有load/store指令可以访存
  - 没有condition code

- User ISA：应用程序可见的ISA

  - 数据流，ALU操作，控制流

- System ISA：对OS可见

  - 优先级，控制寄存器，控制处理器，内存，IO等重要资源的指令

- 五级流水：详见PPT35-41

  