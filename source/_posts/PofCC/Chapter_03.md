---
title: 第三章 存储系统
math: true
date: 2023-08-20 16:07:00
---

{% markmap 750px %}

- 存储系统
  - 存储器概述
    - 存储器的分类
      - 按在计算机中的作用（分层）分类
        - 主存储器（主存、内存）
          - 定义：用来存放计算机运行期间所需的程序和数据，CPU可以直接随机地对其进行访问，也可以和高速缓冲存储器及辅助存储器交换数据。
          - 特点：
            - 容量小
            - 存取速度快
            - 每位的价格高
        - 辅助存储器(辅存、外存)
          - 定义：用来存放当前暂时不用的程序和数据，以及一些需要永久性保存的信息。辅存的内容需要调入内存后才能被CPU访问。
          - 特点：
            - 容量大
            - 存取速度较慢
            - 单位成本低
        - 高速缓冲存储器(Cache)
          - 定义：位于主存和CPU之间，用来存放当前CPU经常使用的指令和数据，以便CPU能高速地访问他们。
          - 特点
            - 存储容量小
            - 存取速度较快
            - 价格高
      - 按存储介质分类
        - 磁表面存储器
          - 磁盘
          - 磁带
        - 磁芯存储器
          - 硬盘
        - 半导体存储器
          - MOS型存储器
          - 双极型存储器
        - 光盘存储器
          - 光盘
      - 按存取方式分类
        - 随机存储器（RAM）
          - 定义：存储器中的任何一个存储单元都可以随机存取，而且存取时间与存取单元的物理位置无关
          - 优点：
            - 读写方便
            - 使用灵活
          - 作用：用作主存或高速缓冲存储器
          - 分类：
            - 静态RAM
            - 动态RAM
        - 只读存储器（ROM）
          - 定义：存储器的内容只能随机读出而不能写入。信息一旦写入存储器就固定不变，即使断电，内容也不会丢失。
          - 作用：
            - 用它存放固定不变的程序、常数和汉字字库等
            - 它与RAM可共同作为主存的一部分，同一构成主存的地址域
          - 分类
            - ROM
            - PROM
            - EPROM
            - EEPROM
            - Flash
        - 串行访问存储器
          - 定义：对存储单元进行读/写操作时，需按其物理位置的先后顺序寻址
          - 分类
            - 顺序存取存储器(磁带)
              - 定义：存储器的内容只能按某种顺序存取，存取时间的长短与信息在存储体上的物理位置有关
              - 特点：存取速度慢
            - 直接存取存储器(磁盘、光盘)
              - 存取信息时通常先寻找整个存储器的某个小区域，再在小区域内顺序查找。
      - 按信息的可保存性分类
        - 易失性存储器：断电后，存储信息即消失的存储器
        - 非易失性存储器：断电后信息仍然保持的存储器
        - 破坏性读出：若某个存储单元所存储的信息被读出后，原存储信息被破坏。
        - 非破坏性读出：若读出时，被读单元原存储信息不被破坏。
        - 具有破坏性读出的存储器，每次读出操作后，必须紧接着一个再生的操作，以便恢复被破坏的信息
    - 存储器的性能指标
      - 存储容量
        - 存储容量=存储字数$\times$字长
        - 单位换算：1B=8b
        - 存储字数：表示存储器的地址空间的大小
        - 字长：表示一次存取操作的数据量
      - 单位成本
        - 每位价格=总成本/总容量
      - 存取速度
        - 数据传输率=数据的带宽/存取周期
        - 存取时间（$T_a$）：指从启动一次存储器操作到完成该操作所经历的时间，分为读出时间和写入时间
        - 存取周期($T_m$)：又叫写周期或访问周期，是指存储器进行一次完整的读写操作所需的全部时间，即连续两次独立访问存储器操作之间所需要的最小时间间隔
        - 主存带宽($B_m$)：又叫数据传输率，表示每秒从主存进出信息的最大数量
      - 设计存储器系统目的：大容量、低成本、高速度
      - 存取时间($T_a$)和存取周期($T_m$)之间的关系：通常情况下，存取周期大于存取时间，因为在任何存取器中，在读写操作之后，都一段恢复内部状态的复原时间。
    - 多级层次的存储系统
      - Cache—主存层：解决CPU和主存速度不匹配问题
      - 主存—辅存层：解决存储系统的容量问题。
      - 在存储系统中，Cache、主存能够与CPU直接交换信息，辅存则需要通过主存与CPU间接交换信息
      - 主存能够直接与CPU、Cache、辅存交换信息
      - 三级存储系统的层次结构
        - ![三级存储系统层次结构图](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E4%B8%89%E7%BA%A7%E5%AD%98%E5%82%A8%E7%B3%BB%E7%BB%9F%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84%E5%9B%BE.png)
      - 主存和Cache之间的数据调用是由硬件来完成的，对所有程序员均是透明的；而主存和辅存之间的数据调动则是由硬件和操作系统共同完成，对应用程序员是透明的。
    
  - 主存储器
    
    - 主存由DRAM实现
    
    - 靠近处理器的Cache由SRAM实现
    
    - DRAM和SRAM都属于易失性存储器
    
    - SRAM的速度比DRAM更快，价格更昂贵
    
    - ROM属于非易失性存储器
    
    - SRAM芯片和DRAM芯片
    
      - 存储元：存放一个二进制位的物理器件，是存储器的最基本的构件
    
      - 存储单元：地址码相同的多个存储元构成一个存储单元
    
      - 存储体：若干个存储单元的集合
    
      - SRAM的工作原理
    
        - 用双稳态触发器来记忆信息的，因此即使信息被读出后，它仍然保持其原状态而不需要再生（非破坏性读出）
        - 优点
          - 存取速度快
        - 缺点
          - 集成度低
          - 功耗大
          - 价格昂贵
        - 应用： 用于Cache
    
      - DRAM的工作原理
    
        - 利用存储元电路中栅极电容上的电荷来存储信息的。DRAM的基本存储元通常只使用一个晶体管，故比SRAM的密度高得多。
    
        - 与SRAM相比的优点
    
          - 集成度高
          - 价位低
          - 容量大
          - 功耗低
    
        - 与SRAM相比的缺点
    
          - 速度慢
    
        - 应用：用于主存
    
        - DRAM的刷新
    
          - 刷新周期：2ms
          - 刷新方式
            - 集中刷新：在一个刷新周期内，利用一段固定的时间，依次对存储器的所有行进行逐一再生，在此期间停止对存储器的读写操作，称为“死时间”，又称访存“死区”
              - 优点：读写操作时不会受到刷新工作的影响
              - 缺点：在集中刷新期间（死区）不能访问存储器
            - 分散刷新：把对每行的刷新分散到各个工作周期中。这样，一个存储器的工作周期分为两个部分：前半部分用于正常的读、写或保持；后半部分用于刷新。
              - 优点：没有死区
              - 缺点：加长了系统的存取周期，降低了整机的速度
            - 异步刷新：将刷新周期除以行数，得到两次刷新操作之间的时间间隔t，利用逻辑电路每隔时间t产生一次刷新请求
              - 作用：避免使CPU连续等待过长的时间，而且降低了刷新次数，从根本上提高了整机的刷新
          - DRAM的刷新需要注意的问题
            - 刷新对CPU是透明的，即刷新不依赖于外部的访问
            - 动态RAM的刷新单位是行，由芯片内部自行生成行地址
            - 刷新操作类似于读操作，但又有所不同
            - 刷新时不需要选片，即整个存储器中的所有芯片同时被刷新
    
        - DRAM芯片的读写周期
    
          - $\overline{RAS}$—行选通信号
          - $\overline{CAS}$—列选通信号
          - 在读周期中，为使芯片能够正确接收行、列地址，在$\overline{RAS}$有效前将行地址送到芯片的地址引脚，$\overline{CAS}$滞后$\overline{RAS}$一段时间，在$\overline{CAS}$有效前将列地址送往芯片的地址引脚，$\overline{RAS}$和$\overline{CAS}$应至少保持$t_{RAS}$和$t_{CAS}$的时间。在读周期中$\overline{WE}$为高电平，并在$\overline{CAS}$有效前建立
          - ![DRAM芯片读周期时序图](https://gitee.com/fangcongss/blog-pic/raw/master/img/DRAM%E8%8A%AF%E7%89%87%E8%AF%BB%E5%91%A8%E6%9C%9F%E6%97%B6%E5%BA%8F%E5%9B%BE.png)
          - 在写周期中，行列选通的时序关系和读周期相同。在写周期中$\overline{WE}$为低电平，同样在$\overline{CAS}$有效前建立。为了保证数据可靠地写入，写数据必须在$\overline{CAS}$有效前在数据总线上保持稳定。
          - 
        
        - SRAM和DRAM的比![DRAM芯片写周期时序图](https://gitee.com/fangcongss/blog-pic/raw/master/img/DRAM%E8%8A%AF%E7%89%87%E5%86%99%E5%91%A8%E6%9C%9F%E6%97%B6%E5%BA%8F%E5%9B%BE.png)较
        
          - |            | SRAM   | DRAM     |
            | ---------- | ------ | -------- |
            | 存储信息   | 触发器 | 电容     |
            | 破坏性读出 | 非     | 是       |
            | 需要刷新   | 不要   | 要       |
            | 送行列地址 | 同时送 | 分两次送 |
            | 运行速度   | 快     | 慢       |
            | 集成度     | 低     | 高       |
            | 存储成本   | 高     | 低       |
            | 主要用途   | Cache  | 主存     |
        
        - 存储芯片的内部结构
        
          - 存储体：存储单元的集合，它由行选线(X)和列选线(Y)来选择所访问单元，存储体的相同行、列上的位同时被读出或写入。
          - 地址译码器：用来将地址转换为译码输出线上的高电平，以便驱动相应的读写电路
          - I/O控制电路：用以控制被选中的单元的读出或写入，具有放大信息的作用
          - 偏选控制信号：单个芯片的容量小，往往满足不了计算机对存储器容量的要求，因此需要一定数量的芯片进行存储器的扩展。在反问某个字时，必须“选中”该存储字所在的芯片，而其他的芯片不被“选中”，因此需要片选信号。
          - 读/写控制信号：根据CPU给出的读命令或写命令，控制被选中单元进行读或写
          - ![存储芯片结构图](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E5%AD%98%E5%82%A8%E8%8A%AF%E7%89%87%E7%BB%93%E6%9E%84%E5%9B%BE.png)
    
    - 只读存储器
    
      - 只读存储器（ROM）的特点
        - 支持随机访问
        - 一旦有了信息，就不能轻易改变，即使掉电也不会丢失
        - 在计算机系统中是只供读出的存储器
      - ROM的优点
        - 结构简单，所以位密度比可读写存储器的高
        - 具有非易失性，所以可靠性高
      - ROM的类型
        - 掩膜式只读存储器MROM
        - 一次可编程只读存储器PROM
        - 可擦除可编程只读存储器EPROM
        - Flash存储器
        - 固态硬盘SSD
    
    - 主存储器的基本组成
    
      - 编址单位：指具有相同地址的那些存储元件构成的一个单元，可以按字节编址，也可以按字编址
      - 现代计算机通常采用按字节编址，此时存储体内的一个地址中有1个字节
      - 指令执行过程中需要访问主存时，CPU首先把被访问单元的地址送到MAR中，然后通过地址线将主存地址送到主存的MAR中，以便于地址译码器进行译码选中相应单元，同时CPU将读写信号通过控制线送到主存的读写控制电路。
      - 如果是写操作，CPU同时将要写的信息送到MDR中，在读写控制电路的控制下，经数据线将信号写入到选中的单元；如果是读操作，主存读出选中单元的内容送到数据线，然后送到MDR中
      - 数据线的宽度与MDR的宽度相同，是存储单元的整数倍
      - 地址线的位数决定了主存地址空间的最大可寻址范围。
      - 通常采用地址线分时复用技术，将行地址和列地址通过相同的引脚分先后两次输入，这样地址引脚数可以减少一半。
      - ![主存储器的基本组成框图](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E4%B8%BB%E5%AD%98%E5%82%A8%E5%99%A8%E7%9A%84%E5%9F%BA%E6%9C%AC%E7%BB%84%E6%88%90%E6%A1%86%E5%9B%BE.png)
    
    - 多模块存储器
    
      - 多模块存储器是一种空间并行技术，利用多个结构完全相同的存储模块的并行工作来提高存储器的吞吐率/
      - 单体多字存储器
        - 特点：存储器中只有一个存储体，每个存储单元存储m个字，总线宽度也为m个字。一次并行读出m个字，地址必须顺序排列并处于同一存储单元。
        - 单体多字系统的执行过程
          - 在一个存储周期内，从同一地址取出m条指令，然后将指令逐条送至CPU执行，即每隔1/m个存取周期，CPU向主存取一条指令。
        - 缺点
          - 指令和数据在主存内必须是连续存放的，一旦遇到转移指令，或操作数不能连续存放，这中方式的效果就不明显。
      - 多体并行存储器
        - 多体并行存储器由多体模块组成
        - 每个模块都有相同的容量和存取速度，个模块都有独立的读写控制电路、地址寄存器和数据寄存器
        - 它们既能并行工作，又能交叉工作
        - 高位交叉编址（顺序方式）
          - 高位地址表示体号，低位表示体内地址
          - 把低位的体内地址送到由高位体号确定的模块内进行译码
          - 访问一个连续主存块时，总是先在一个模块内访问，等到该模块访问完才转到下一个模块访问，CPU总是按顺序访问存储模块，各模块不能倍并行访问，因而不能提高存储器的吞吐率。
          - ![高位交叉编址的多提存储器](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E9%AB%98%E4%BD%8D%E4%BA%A4%E5%8F%89%E7%BC%96%E5%9D%80%E7%9A%84%E5%A4%9A%E6%8F%90%E5%AD%98%E5%82%A8%E5%99%A8.png)
        - 低位交叉编址（交叉方式）
          - 低位表示体号，高位表示体内地址
          - 每个模块按“模m”交叉编址
          - 模块号=单元地址%m
          - 假设有m个模块，每个模块有k个单元，则$0,m,\cdots,(k-1)m$单元位于模块$M_0$；$1,m+1,\cdots,(k-1)(m+1)$单元位于模块$M_0$；依此类推。
          - 低位交叉方式下，总是把高位的体内地址送到由低位体号确定的模块内进行译码。
          - 程序连续存放在相邻模块中，一次采用次种编址方式的存储器又叫交叉存储器
          - 采用低位交叉编址后，可在不改变每个模块存取周期的前提下，采用流水线的方式并行存取，提高存储器的带宽。
          - ![低位交叉编址的多体存储器](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E4%BD%8E%E4%BD%8D%E4%BA%A4%E5%8F%89%E7%BC%96%E5%9D%80%E7%9A%84%E5%A4%9A%E4%BD%93%E5%AD%98%E5%82%A8%E5%99%A8.png)
          - 低位交叉编址相关计算
            - 模块字长等于数据总线带宽
            - 模块存取一个字的存取周期为T
            - 总线传送周期为r
            - 实现流水线存取，则交叉模块数量m满足公式$m\ge T/r$
            - m叫做交叉存取度。
            - 每经过r时间的延迟启动下一个模块，交叉存储器要求其模块数必须大于等于m，以保证启动某个模块后经过$m\times r$时间后再次启动该模块时，其上次的存取操作已经完成。
            - 连续存取m个字所需要的时间$t_1=T+(m-1)r$
            - ![低位交叉编址流水线方式存取示意图-1](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E4%BD%8E%E4%BD%8D%E4%BA%A4%E5%8F%89%E7%BC%96%E5%9D%80%E6%B5%81%E6%B0%B4%E7%BA%BF%E6%96%B9%E5%BC%8F%E5%AD%98%E5%8F%96%E7%A4%BA%E6%84%8F%E5%9B%BE-1.png)
    
  - 主存储器与CPU的连接
    - 连接原理
      - 主存储器通过数据总线、地址总线和控制总线与CPU连接
      - 数据总线的位数与工作频率的乘积正比于数据传输率
      - 地址总线的位数决定了可寻址的最大内存空间
      - 控制总线（读/写）指出总线周期的类型和本次输入/输出操作完成的时刻
    - 主存容量的扩展
      - 位扩展法：用多个芯片对字长进行扩充，增加存储字长，使其数据位数与CPU的数据线数相等。
        - 连接方式：将多个存储芯片的地址端、偏选端和读写控制端相应并联，数据端分别引出。
        - 仅采用位扩展时，各芯片连接地址线的方式相同，但连接数据线的方式不同，在某一时刻选中所有的芯片，所以片选信号$\overline{CS}$要连接到所有芯片
        - ![位扩展连接示意图](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E4%BD%8D%E6%89%A9%E5%B1%95%E8%BF%9E%E6%8E%A5%E7%A4%BA%E6%84%8F%E5%9B%BE.png)
      - 字扩展法：增加存储器中字的数量，而位数不变。
        - 连接方式：字扩展将芯片的地址线、数据线、读写控制线相应并联，而由偏选信号来区分各芯片的地址范围。
        - 仅采用字扩展时，各芯片连接地址线的方式相同，连接数据线的方式也相同，但在某一时刻需要选中部分芯片，所以通过片选信号或采用译码器设计连接到相应的芯片
        - ![字扩展连接示意图](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E5%AD%97%E6%89%A9%E5%B1%95%E8%BF%9E%E6%8E%A5%E7%A4%BA%E6%84%8F%E5%9B%BE.png)
      - 字位扩展法（位扩展和字扩展的结合）
        - 采用字位扩展时，各芯片连接地址线的方式相同，但连接数据线的方式不同，而需要通过片选信号或采用译码器设计连接到相应的芯片
    - 存储芯片与CPU的连接
      - 实现CPU对存储单元访问的过程
        - 第一步，片选（选择存储芯片）
        - 第二步，字选（将选中的芯片依地址码选择相应的存储单元，以进行数据的存取
        - 片内的字选通常是由CPU送出的N条低位地址线完成的，地址线直接接到所有芯片的地址输入端
      - 片选信号的产生方式
        - 线选法
          - 用除片内寻址外的高位地址线直接（或经反相器）分别连到各个存储芯片的片选端
          - 当某地址信息为“0”时，就选中与之对应的存储芯片。
          - 这些片选地址线每次寻址只能有一位有效，不允许同时有多位有效，这样才能保证一次只选中一片芯片。
        - 译码片选法
          - 用除片内寻址外的高位地址线通过地址译码器产生片选信号
    - 存储器与CPU的连接
      - 合理选择存储芯片
        - 存储芯片的类型
        - 存储芯片的数量
        - 通常选用ROM存放系统程序、标准子程序和各类常数
        - 选中RAM为用户编程而设置
        - 在考虑芯片数量时，尽量连线简单、方便
      - 地址线的连接
        - CPU地址线的低位与存储芯片的地址线连接，以选择芯片中的某一单元（字选），这部分的译码是由芯片内的片内逻辑完成的。
        - CPU地址线的高位在扩充存储芯片时使用，用来选择存储芯片（片选），这部分译码由外接译码器逻辑完成。
      - 数据线的连接
        - CPU的数据线数与存储芯片的数据数不一定相等，在相等时可直接连接；在不相等时必须对存储芯片扩位，使其数据位数与CPU的数据线相等。
      - 读/写命令线的连接
        - 直接与存储芯片的读/写控制端相连，通常高电平为读，低电平为写。
      - 片选线的连接
    
  - 外部存储器
    - 磁盘存储器
      - 优点
        - 存储容量大，位价格低
        - 记录介质可重复使用
        - 记录信息可长期保存而不丢失，甚至可脱机存档
        - 非破坏性读出，读出时可以不考虑再生
      - 缺点
        - 存取速度慢，机械结构复杂，对工作环境要求高
      - 磁盘设备的组成
        - 磁盘驱动
          - 磁头组件
          - 盘片组件
        - 磁盘控制器：硬盘存取器和主机的接口，主流标准由IDE、SCSI、SATA
        - 盘片
      - 存储区域：一块磁盘包含若干盘面，每个盘面划分为若干磁道，每条磁道又划分为若干扇区，扇区是磁盘读写的最小单位，即磁盘按块存取。
        - 磁头数：又叫记录面数，表示硬盘共有多少个磁头，磁头用于读取/写入盘片上记录面的信息，一个记录面对应一个磁头
        - 柱面数：表示硬盘每面盘片上有多少条磁道
        - 扇区数：表示每条磁道上有多少个扇区
      - 磁记录原理
        - 原理：磁头和磁性记录介质相对运动时，通过电磁转换完成读/写操作
        - 编码方式：按某种方案，把一连串的二进制信息转换成存储介质磁层中一个磁化翻转状态序列，并使读/写控制电路容易、可靠地实现转换
        - 磁记录方式：通常采用调频制（FM）和改进型调频制（MFM）的记录方式
      - 磁盘性能指标
        - 记录密度：盘面单位单位面积记录的二进制信息量。
          - 单位：
            - 道密度：沿磁盘半径方向单位长度上的磁道数
            - 位密度：磁道单位长度上能记录的二进制位数
            - 面密度：位密度与道密度的乘积
        - 磁盘的容量：
          - 非格式化容量：磁记录表面可利用的磁化单元总数
          - 格式化容量：按照某种特定的记录格式所能存储信息的总量
          - 格式化后的容量比非格式化容量要小
        - 平均存取时间：寻道时间+旋转延迟时间+传输时间
          - 寻道时间：磁头移动到目的磁道所花的时间
          - 旋转延迟时间：磁头定位到要读写的扇区的时间
          - 传输时间：传输数据所花费的时间
          - 寻道时间和旋转延迟时间都取平均值
        - 数据传输率：磁盘存储器在单位时间内向主机传送数据的字节数
      - 磁盘地址
        - 驱动器号+柱面（磁道）号+盘面号+扇区号
      - 磁盘的工作过程
        - 寻址
        - 读盘
        - 写盘
      - 磁盘阵列
        - RAID：独立冗余磁盘阵列，是指将多个独立的物理磁盘组成一个独立的逻辑盘，数据在多个物理盘上分割交叉存储、并行访问，具有更好的存储性能、可靠性和安全性。
        - RAID0:无冗余和无校验磁盘阵列，提高了存取速度，但没有容错能力
        - RAID1:镜像磁盘阵列
        - RAID2:采用纠错的海明码磁盘阵列
        - RAID3:位交叉奇偶校验的磁盘阵列
        - RAID4:块交叉奇偶校验的磁盘阵列
        - RAID5:无独立校验的奇偶校验磁盘阵列
      - RAID的功能
        - 使用多个磁盘，提高传输率
        - 通过在多个磁盘上并行存取来大幅提高存储系统的数据吞吐量
        - 通过镜像功能，提高安全可靠性
        - 通过数据校验，提供容错能力
    - 固态硬盘
    
  - 高速缓冲存储器
    - 程序访问的局部性原理
      - 时间局部性：在最近的未来要用到的信息，很可能是现在正在使用的信息，因为程序中存在循环
      - 空间局部性：在最近的未来要用到的信息，很可能与现在正在使用的信息在存储空间上是邻近的，因为指令是顺序存放、顺序执行，数据一般也是以向量、数组等形式簇聚地存储在一起
    - Cache的基本工作原理
      - Cache和主存都被划分为相等的块
      - Cache块（Cache行）
        - 由若干字节组成
        - （Cache长）块长：块的长度
      - Cache中的块数远小于主存中的块数，所以Cache中存放的是最活跃的若干块的副本。
      - Cache按照某种策略，预测CPU在未来一段时间内欲访存的数据，将其装入Cache。
      - Cache的工作过程
        - 当CPU发送读请求时，若访存地址在Cache中命中，就将此地址转换为Cache地址，直接对Cache进行读操作，与主存无关
        - 若Cache不命中，则仍需要访问主存，并把此字所在的块一次性地从主存调入Cache
        - 若此时Cache已满，需要根据某种替换算法，用这个块替换Cache中原来的某块信息。
        - 整个过程全部由硬件实现
        - CPU与Cache之间的数据交换以字为单位，而Cache与主存之间的数据交换则以Cache块为单位。
        - 某些计算机中也采用同时访问Cache和主存的方式，若Cache命中，则存储访问终止；否则访问主存并替换Cache
        - 当CPU发出写请求的时候，若Cache命中，有可能出现Cache与主存的内容不一致的情况，所以若Cache命中，需要按照一定的策略处理
          - 全写法
          - 回写法
        - ![Cache的工作原理图](https://gitee.com/fangcongss/blog-pic/raw/master/img/Cache%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86%E5%9B%BE.png)
        - Cache命中率：CPU欲访问的信息在Cache中的比率
          - 计算方法：
            - $H=N_c/(N_c+N_m)$
            - H为命中率
            - $N_c$为Cache的总命中次数
            - $N_m$为访问主存的总次数
        - Cache—主存系统的平均访问时间
          - 计算方法
            - $T_a=Ht_c+(1-H)t_m$
            - $T_a$为平均访问时间
            - $H$为命中率
            - $t_c$为命中时的Cache访问时间
            - $t_m$为未命中的访问时间
        - 根据Cache的读写流程，实现Cache是需要解决的问题
          - 数据查找：如何快速判断数据是否在Cache中
          - 地址映射：主存如何存放在Cache中，如何将主存地址转换为Cache地址
          - 替换策略：Cache满后，使用何种策略对Cache块进行替换或淘汰
          - 写入策略：如何即保证主存块和Cahce块的数据一致性，有尽量提高效率
    - Cache和主存的映射方式
      - 直接映射：Cache行号=主存块号 mod Cache总行数
        - 主存直接映射的地址结构：标记+Cache行号+块内地址
        - 设Cache有$2^c$行，主存有$2^m$块，则标记位数$t=m-c$,Cache行号位数为$c$,则块内地址位数为$b$
        - 在直接映射下，CPU的访存过程
          - ![CPU访存过程](https://gitee.com/fangcongss/blog-pic/raw/master/img/CPU%E8%AE%BF%E5%AD%98%E8%BF%87%E7%A8%8B.png)
          - 根据访存地址中的c位，找到对应的Cache行，将对应的Cache行中的标记和主存地址的高t位标记进行比较，若相等且有效位为1，则访问Cache“命中”，此时根据主存地址中低位的块内地址，在对应的Cache行中存储信息；
          - 若不相等或有效位为0，则“不命中”，此时CPU从主存中读出该地址所在的一块信息送到对应的Cache行中，将有效位置1，并将标记设置为地址中的高t位，同时将该地址中的内容送往CPU。
      - 全相联映射
        - 主存中的每一块可以装入Cache中的任何位置，每行的标记用于指出该行取自主存哪一块，所以CPU访存时需要与所有Cache进行比较。
        - 优点
          - 灵活
          - Cache块的冲突概率低
          - 空间利用率高
          - 命中率高
        - 缺点
          - 标记的比较速度慢
          - 实现成本高
        - 全相联映射下，主存地址结构：标记+块内地址
      
      - 组相联映射
        - 将Cache分为Q个大小相等的组，每个主存块可以装入固定组中的任意行，即组间采用直接映射、而组内采用全相联映射的方式。
        - 当Q=1时变为全相联映射，当Q=Cache行数时变为直接映射。
        - 组相联映射的关系定义：Cache组号=内存块号 mod Cache组数（Q）
        - 组相联映射下，主存地址结构：标记+Cache组号+块内地址
        - 在组相联映射下，CPU访存过程
          - 根据访存地址中的组号找到对应的Cache组
          - 将对应Cache组中每个行的标记与主存地址的高位地址进行比较
          - 若有一个相等且有效位为1，则访问Cache命中，此时根据主存地址中的块内地址，在对应Cache行中存取信息
          - 若都不相等或虽然相等但有效位为0，则不命中，此时CPU从主存中读出该地址所在的一块信息送到对应Cache组中的任意一个空闲行中，将有效位置1，并设置标记，同时将该地址中的内容送往CPU。
    - Cache中主存块的替换算法
    
      - 全相联映射与组相连映射需要替换算法，而直接映射不需要替换算法。
      - 常用替换算法
        - 随机（RAND）算法
          - 随机地确定替换的Cache块。
          - 优点：实现比较简单
          - 缺点：由于未依据程序局部访问原理，因此可能命中率较低
        - 先进先出（FIFO）算法
          - 依据程序访问的局部性原理，选择近期内长久未访问过的Cache行作为替换的行，平均命中率要比FIFO的高，是堆栈类的算法
        - 近期最少使用（LRU）算法
          - 依据程序访问的局部性原理，选择近期长期未访问过的Cache行作为替换的行，因为最早进入的主存块也可能是目前经常要用的。
        - 最不经常使用（LFU）算法
          - 将一段时间内被访问次数最少的存储行换出。
    - Cache写策略
      - 目的：使Cache内容与主存内容保持一致
      - 对于Cache写命中，有两种处理方法
        - 全写法（写直通法、write-through）
          - 当CPU对Cache写命中时，必须把数据同时写入Cache和主存。
          - 当某一块需要替换时，不必把这一块写回主存，用新调入的块直接覆盖
          - 优点：实现简单，能随时保持主存数据的正确性
          - 缺点：增加了访存次数，降低了Cache的访存
          - 写缓冲：为减少全写法直接写入主存的时间消耗，在Cache和主存之间加入一个写缓冲。
          - ![带有写缓冲的Cache](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E5%B8%A6%E6%9C%89%E5%86%99%E7%BC%93%E5%86%B2%E7%9A%84Cache.png)
          - CPU同时写数据到Cache和写缓冲中，写缓冲再控制将内容写入主存。
          - 写缓冲是一个FIFO队列，写缓冲可以解决速度不匹配的问题。
          - 若出现频繁写时，会使写缓冲饱和溢出
      - 回写法（write-back）
        - 当CPU对Cache写命中时，只把数据写入Cache，而不立即写回主存，只有当此块被换出时才会写回主存。
        - 优点：减少访存次数
        - 缺点：存在不一致的隐患
        - 为了减少写回主存写回主存的开销，每个Cache行设置一个修改位（脏位）。
        - 若修改位为1，则说明Cache行中的块未被修改，替换时无须写回主存。
    - 对于Cache写不命中，也有两种处理方法
      - 写分配法
        - 加载主存中的块到Cache中，然后更新这个Cache块。
        - 写分配法试图利用程序的空间局部性，但缺点是每次不命中都需要从主存中读取一块。
      - 非写分配法
        - 只写入主存，不进行调块
    - 非写分配法与全写法结合使用，写分配法与回写法结合使用。
    - 统一Cache结构
      - 优点：设计和实现简单
      - 缺点：由于执行部件存取数据时，指令预取部件要从同一Cache读指令，会引发冲突。
    - 分离Cache结构：将指令Cache和数据 Cache分开设计
      - 解决了指令预取部件从同一Cache读指令引发冲突问题
      - 分离的指令和数据Cache还可以充分利用指令和数据的不同局部性来优化性能。
    - 指令Cache和数据Cache分离一般在L1级  
    
  - 虚拟存储器
    
    - 主存和辅存共同构成了虚拟存储器，二者在硬件和软件的共同管理下工作。
    - 虚拟存储器的基本概念
      - 将主存活辅存的地址空间统一编址，形成一个庞大的地址空间，在这个地址空间中用户可以自由编程，而不必在乎实际的主存容量和程序在主存中实际的存放位置。
      - 虚地址（逻辑地址）：用户允许涉及的地址。
      - 虚拟空间（程序空间）：虚地址对应的存储空间
      - 实地址（物理地址）：实际的主存单元地址
      - 主存地址空间（实地址空间）：实地址对应的存储空间
      - 虚拟存储器的3个地址空间
        - ![虚拟存储器的三个地址空间](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E8%99%9A%E6%8B%9F%E5%AD%98%E5%82%A8%E5%99%A8%E7%9A%84%E4%B8%89%E4%B8%AA%E5%9C%B0%E5%9D%80%E7%A9%BA%E9%97%B4.png)
        - CPU使用虚拟地址的访存过程
          - CPU使用虚地址时，由辅助硬件找出虚地址和实地址之间的对应关系，并判断这个虚地址对应的存储单元内容是否已经装入主存。
          - 若已在主存中，则通过地址变换，CPU可直接访问主存指示的实际单元
          - 若不在主存中，则把包含这个字的一页或一段调入主存后在由CPU访问。
          - 若主存已满，则采用替换算法置换主存中的交换块（即页面）
        - 虚拟存储器也采用和Cache类似的技术，将辅存中经常访问的数据副本存放到主存中。
        - 缺页（或段）而访问辅存的代价很大，提高命中率是关键，因此虚拟存储机制采用全相联映射，每个虚页面可以存放到对应主存区域的任何一个空闲页位置
        - 当进行写操作时，不能每次写操作都同时写回磁盘，因而，在处理一致性问题时，采用回写法。
    - 页式虚拟存储器
      - 页为基本单位
      - 虚拟空间与主存空间都被划分成同样大小的页。
      - 实页（页框）：主存的页
      - 虚页：虚存的页
      - 虚拟地址：虚拟页号+页内地址
      - 虚拟地址到物理地址的转换是由页表实现的
      - 页表：一张存放在主存中的虚页号和实页号的对照表，它记录程序的虚页调入主存时被安排在主存中的位置。
        - 页表一般长期地保存在内存中。
        - 页表组成
          - 有效位（装入位）：用来表示对应页面是否在主存，若为1，则表示该虚拟页已从外存掉入内存，此时页表项存放的是该页的物理页号；若为0，则表示表示没有调入主存，此时页表项可以存放该页的磁盘地址。
          - 脏位（修改位）：用来表示页面是否被修改过，虚拟机制中采用回写策略，利用脏位可判断替换时是否需要写回磁盘。
          - 引用位（使用位）：用来配合替换策略进行设置
          - 物理页或磁盘地址
        - 页式虚拟存储器的地址变换过程
          - ![页式存储器的地址变换过程](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E9%A1%B5%E5%BC%8F%E5%AD%98%E5%82%A8%E5%99%A8%E7%9A%84%E5%9C%B0%E5%9D%80%E5%8F%98%E6%8D%A2%E8%BF%87%E7%A8%8B.png)
          - CPU执行指令时，需要先将虚拟地址转换为主存物理地址。
          - 页表基址寄存器存放进程的页表收地址，然后根据虚拟地址高位部分的虚拟页号找到对应的页表项，若装入位为1，则取出物理页号，和虚拟地址的低位部分的页内地址拼接，形成实际物理地址
          - 若装入位为0，则说明缺页，需要操作系统进行缺页处理。
        - 页式虚拟存储的优点
          - 页面的长度固定
          - 页表简单
          - 调入方便
        - 页式虚拟存储的缺点
          - 程序不可能正好是页面的整数倍，最后一页的零头将无法利用而造成浪费，并且页不是逻辑上独立的实体，所以处理、保护和共享都不及段式虚拟存储器方便
      - 块表（TLB）
        - 一个用于存放最近经常访问的页面的高速缓冲器
        - 优点：明显提高效率
        - 慢表：存放在主存中的页表
        - 具有块表的页式虚拟存储器的地址转换过程
          - 首先查找快表，若命中，则无须访问主存中的页表
        - 快表通常采用全相联映射或组相连映射
        - TLB项=表项内容+TLB标记字段
        - TLB标记：表示该表项取自页表中的哪个虚页号对应的页表项，因此，TLB标记的内容在全相联映射方式下就是该页表项对应的虚页号；组相连映射方式下则是对应虚页号的高位部分，而虚页号的地位部分用于选择TLB组的组索引
      - 具有TLB和Cache的多级存储系统
        - TLB和Cache的访问过程
          - CPU给出一个32位的虚拟地址，TLB采用全相联方式，每一项都有一个比较器，查找时将虚页号与每个TLB标记字段同时进行比较，若有某一项相等且对应有效位为1，则TLB命中，此时可直接通过TLB进行地址转换
          - 若未命中，则TLB缺失，需要访问主存去查页表。
          - 图中所示的是两级页表方式，虚页号被分为页目录索引和页表索引两个部分，由这两个部分得到对应的页表项，从而进行地址转换后，Cache机构根据映射方式将方式将物理地址中的高位部分进行比较，若相等且对应有效位为1，则Cache命中，此时根据块内地址取出对应的字送往CPU。
          - ![TLB和Cache的访问过程](https://gitee.com/fangcongss/blog-pic/raw/master/img/TLB%E5%92%8CCache%E7%9A%84%E8%AE%BF%E9%97%AE%E8%BF%87%E7%A8%8B.png)
          - 在一个具有Cache和TLB的虚拟存储系统中，CPU反问过程中存在的三种缺失情况
            - TLB缺失：要访问的页面的页表项不在TLB中
            - Cache缺失：要访问的主存块不在Cache中
            - Page缺失：要访问的页面不在主存中。
            - ![带TLB虚拟存储过程的CPU访存过程](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E5%B8%A6TLB%E8%99%9A%E6%8B%9F%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E7%9A%84CPU%E8%AE%BF%E5%AD%98%E8%BF%87%E7%A8%8B.png)
    - 段式虚拟存储器
    - 段页式虚拟存储器
    - 虚拟存储器与Cache的比较

{% endmarkmap %}

### 存储概述

#### 存储分类

| 分类                           | 描述                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| 按在计算机中的作用（层次）分类 | 1. 主存储器<br>2. 辅存储器<br>3. 高速缓存器                  |
| 按存储介质分类                 | 1. 磁表面存储(磁带)<br>2. 磁芯存储器(磁盘)<br>3. 半导体存储器(MOS、双极型)<br>4. 光存储器(光盘) |
| 按存取方式分类                 | 1. 随机存储器<br>2. 只读存储器<br>3. 串行访问存储器: 顺序存取和直接存取 |
| 按信息的可保存性分类           | 易失性存储器和非易失性存储器                                 |

#### 存储器性能指标

| 性能指标                              | 单位        | 描述                                                         |
| ------------------------------------- | ----------- | ------------------------------------------------------------ |
| 容量=存储字数$\times$字长             | B, KB,MB,GB |                                                              |
| 价格:单位价格=总容量/总成本           | B/Y         |                                                              |
| 速度:数据传输率 = 数据的带宽/存取周期 | B/s         | 存取时间=从启动一次存储器操作到完成该操作所经历的时间<br>存储周期=连续两次独立访问存储器操作之间的最小时间间隔 |

