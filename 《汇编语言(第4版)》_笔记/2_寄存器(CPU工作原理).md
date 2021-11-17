—————————————————
2.1.通用寄存器
2.2.字在寄存器中的存储
2.3.几条汇编指令
2.4.物理地址
2.5.16位结构的CPU
2.6.8086CPU给出物理地址的方法
2.7.“段地址*16+偏移地址=物理地址”的本质含义
2.8.段的概念
2.9.段寄存器
2.10.CS和IP
2.11.修改CS、IP的指令
2.12.代码段
—————————————————

一个典型的CPU由运算器、控制器、寄存器(CPU工作原理)等器件组成，这些器件靠内部总线相连

内部总线实现CPU内部各个器件之间的联系，外部总线实现CPU和主板上其他器件的联系

在CPU中：
1）运算器进行信息处理
2）寄存器进行信息存储
3）控制器控制各种器件进行工作
4）内部总线连接各种器件，在他们之间进行数据的传送

对于一个汇编程序员来说，CPU中的主要部件是寄存器，寄存器是CPU中程序员可以用指令读写的部件，程序员通过改变各种寄存器中的内容来实现对CPU的控制

8086CPU有14个寄存器，它们的名称为：
AX，BX，CX，DX，
SI，DI，SP，BP，
CS，IP，
SS，DS，ES，PSW

8086CPU所有的寄存器都是16位的，可以存放两个字节，AX、BX、CX、DX通常用来存放一般性数据被称为通用寄存器
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8shcygwj30e903sdg9.jpg)

一个16位寄存器可以存储一个16位的数据，所能存储的数据的最大值为2^16-1

8086上一代CPU中的寄存器都是8位的，为保证兼容性，这四个通用寄存器都可以分为两个独立的8位寄存器使用
AX可以分为AH和AL
BX可以分为BH和BL
CX可以分为CH和CL
DX可以分为DH和DL
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8ss5p1mj30g605fwfz.jpg)
—————————

出于对兼容性的考虑，8086CPU可以一次性处理以下两种尺寸的数据：
1）字节：记为byte，一个字节由8个bit组成，可以存在8位寄存器中
2）字：记为word，一个字由两个字节组成，这两个字节分别称为这个字的高位字节和低位字节
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8t4abvtj306802hgls.jpg)

为了区分不同的进制，在十六进制表示的数据的后面加H，在二进制表示的数据的后面加B
—————————

在写一条汇编指令或一个寄存器的名称时不区分大小写：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8tjwbmyj30ch03pt9m.jpg)
—————————

CPU访问内存单元时，要给出内存单元的地址，所有的内存单元构成的存储空间是一个一维的线性空间，每一个内存单元在这个空间中都有唯一的地址，我们将这个唯一的地址称为物理地址

CPU通过地址总线送入存储器的，必须是一个内存单元的物理地址。在CPU向地址总线上发出物理地址之前，必须要在内部先形成这个物理地址，不同的CPU可以有不同的形成物理地址的方式
—————————

概括来讲，16位结构描述了一个CPU具有下面几方面的结构特性：
1）运算器一次最多可以处理16位的数据
2）寄存器的最大宽度为16位
3）寄存器和运算器之间的通路为16位
—————————

8086CPU给出物理地址的方法：

8086CPU有20位地址总线，又是16位结构，采用一种在内部用两个16位地址合成的方法来形成一个20位的物理地址
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8u1db7lj30aa06ydgo.jpg)

当8086CPU要读写内存时：
1）CPU中的相关部件提供两个16位的地址，一个称为段地址，另一个称为偏移地址
2）段地址和偏移地址通过内部总线送入一个称为地址加法器的部件
3）地址加法器将两个16位地址合成为一个20位的物理地址
4）地址加法器通过内部总线将20位物理地址送入输入输出控制电路
5）输入输出控制电路将20位物理地址送上地址总线
6）20位物理地址被地址总线传送到存储器
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8ubj36tj30cj06y403.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8ukaiukj30bz08h42f.jpg)

——————————

“段地址*16+偏移地址=物理地址”的本质含义是：CPU在访问内存时，用一个基础地址（段地址*16）和一个相对于基础地址的偏移地址相加，给出内存单元的物理地址
——————————

![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8uth09bj30au066aar.jpg)
在编程时可以根据需要，将若干地址连续的内存单元看作一个段，用段地址*16定位段的起始地址（基础地址），用偏移地址定位段中的内存单元
1）段地址*16必然是16的倍数，所以一个段的起始地址也一定是16的倍数
2）偏移地址为16位，16位地址的寻址能力为64KB，所以一个段的长度最大为64KB
——————————

段地址在8086CPU的段寄存器中存放，8086CPU有4个段寄存器：CS，DS，SS，ES
——————————

CS和IP是8086CPU中两个最关键的寄存器，它们指示了CPU当前要读取指令的地址，CS为代码段寄存器，IP为指令指针寄存器

在8086PC机中，任意时刻，设CS中的内容为M，IP中的内容为N，8086CPU将从内存M*16+N单元开始，读取一条指令并执行
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8w0hau0j30c409hju7.jpg)

8086CPU读取、执行一条指令的过程：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8w92jsrj30c405kq4e.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8wgrgaxj30c405kmym.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8woipllj30c405kgmz.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8wvqrskj30c405k75o.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8x2wtnpj30c405fabk.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8x9k43hj30c405f0u6.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8xguwhdj30c406f0uf.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8xntv5ij30c405edh6.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8xvhssgj30c405vq4c.jpg)

1）从CS：IP指向的内存单元读取指令，读取的指令进入指令缓冲器
2）IP=IP+所读取指令的长度，从而指向下一条指令
3）执行指令，转到步骤1），重复这个过程
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8y47ydgj30c401jwey.jpg)

CPU将CS：IP指向的内存单元中的内容看作指令
—————————

程序员可以通过改变CS、IP中的内容来控制CPU执行目标指令

8086CPU大部分寄存器的值，都可以用mov指令来改变，mov指令被称为传送指令，但是mov指令不能用于设置CS、IP的值；能够改变CS、IP的内容的指令被统称为转移指令（jmp指令）
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8yjgr77j30c402z0tg.jpg)

若想仅修改IP的内容，可用形如“jmp 某一合法寄存器”的指令完成：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8yskyiej30c40383z6.jpg)

——————————
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor8z1g7l7j30cm087gnz.jpg)

