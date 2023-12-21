# 计算机体系结构第三章整理

这里想把每一个PPT的知识点都过一下，最好不要漏。

- 三种dependence
  - data：指令中计算出来数据相互依赖（c=a+b d=c+e）
  - name：两个指令用了同一个reg或者是memory的地址
  - control：指令被一些控制指令（比如branch指令控制）

- Data Hazard

  - RAW：写后读（c=a+b d=c+e）
  - WAR：读后写（c=a+b a=d+e）
  - WAW：写后写（c=a+b c=d+e）

- 三种Hazard

  - Structual hazard：指令i需要一个被后面的指令j要用的资源（有Use）
  - Data hazard：指令i会产生一个后面指令j要用的结果
  - Control hazard：指令i决定后面执行哪条指令
  
- 克服data hazard

  - 使用旁路：如果数据准备好了，直接使用旁路把它放到需要用的地方
  - pipeline interlock：流水线阻塞，直到数据准备好
  
- Dynamic scheduling和乱序执行

  - control-centric: scoreboard
  - data-centric: tomasulo

- Scoarboard Example

  - 关键是分析数据什么时候准备好了，以及什么时候能写回
  - 看完PPT上的example应该就完事了

- Scoreboard局限性

  - 无前递硬件
  - 指令调度基本块内
  - 结构冒险（integer/load store硬件）
  - 结构冒险->暂停发射指令
  - 通过等待处理WAR冒险
  - 防止WAW冒险
  
- Tomasulo特点

  - **换名**：寄存器被数值或者指针代替
  - 消除WAR，WAW冒险，保留站比实际寄存器多，优化一些编译器不能优化的工作
  
- Reservation Stations(RS)

  - operand的一个缓存，全部operand准备好，就enable FU
  - load / store buffer：也是FU
  - 防止寄存器成为性能瓶颈
  - 防止WAR，WAW冒险
  - 用硬件动态完成循环展开
  
- 指令状态

  - Issue：从Fp Op queue拿指令（按序）
  - Exe：执行（可能乱序）
  - 写回：写回结果（可能乱序）
  
- Tomasulo

  - 主要就是少一个状态
  - 每次运算完的东西都写到Register Results Status那里
  - 把图看懂了就好了
  
- RS的缺点

  - 复杂
  - 需要大量相联存储
  - 公共数据总线成为性能瓶颈
  
  
  
  