# 计算机体系结构第五章整理

> C5：画出memory层次，cache层次，cache作用， 冯诺依曼+寄存器+L1 L2 L3cache+memory cache优化方式 cache组织方式 miss cache vs victim cache dram架构

这里想把每一个PPT的知识点都过一下，最好不要漏。

- memory层次的overview

  ![image-20231221183303496](C:\Users\84865\Desktop\mypro\Computer-Architecture-Review\pics\5-1)

- 分支预测

  - 静态：编译器可以去预测（比如基于profile数据和给定的数据）
  - 动态：在程序运行的过程中分支条件可能发生变化

- Reorder Buffer(ROB)

  - 指令格式（分支/ld st/ ALU）
  - 存放的寄存器位置/内存位置
  - Value：指令的结果
  
- Tomasulo+ROB

  - 要放到ROB里面来防止各种数据依赖和conflict
  - 感觉这个过程比较难，需要在PPT里面仔细看清楚
  - 感觉得结合一个视频才能看的懂
  
- VLIW

  - Very Long Instruction Word
  - 一条大语句里面有几个操作

- EPIC

  - Explicitly Parallel Instruction Computing
  - VLIW的一个延申

  

  

  