Debug是DOS、Windows都提供的实模式（8086方式）程序的调试工具，使用它可以查看CPU各种寄存器的内容、内存的情况和在机器码级跟踪程序的运行

Debug功能：
1）R：查看、改变CPU寄存器的内容
2）D：查看内存中的内容
3）E：改写内存中的内容
4）U：将内存中的机器指令翻译成汇编指令
5）T：执行一条机器指令
6）A：以汇编指令的格式在内存中写入一条机器指令
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9276jodj30hs0bstb3.jpg)

1）使用R命令查看、修改CPU中各个寄存器的内容：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor92hm5baj30hu05et8y.jpg)

2）用Debug的D命令查看内存中的内容
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor92q99vmj30hu04i0sv.jpg)

a.中间是从指定地址开始的128个内存单元的内容，用十六进制的格式输出，每行的输出从16的整数倍的地址开始，最多输出16个单元的内容
b.左边是每行的起始地址
c.右边是每个内存单元中的数据对应的可显示的ASCII码字符
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor930ucdxj30hu04ymxb.jpg)

直接使用D命令，将列出Debug预设的地址处的内容
在使用“d 段地址：偏移地址”之后，接着使用D命令，可列出后续的内容
也可以指定D命令的查看范围：“d 段地址：起始偏移地址 结尾偏移地址”
只想查看内存单元10000H中的内容：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor93ch6c2j30hu0163yg.jpg)

3）用Debug的E命令改写内存中的内容
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor93qxd7bj30hu02swej.jpg)

也可以采用提问的方式一个一个的改写内存中的内容：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9420rjyj30hu03c74c.jpg)

可以用E命令向内存中写入字符、字符串
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor94c34y2j30hu02qgln.jpg)

4）用E命令向内存中写入机器码，用U命令查看内存中机器码的含义，用T命令执行内存中的机器码

向内存中写入机器码：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor94lge2hj303z02hglo.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor94yujp2j30hu00x748.jpg)

查看写入的或内存中原有的机器码所对应的汇编指令：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor95a2d9vj30bv07fweq.jpg)

U命令的显示输出分为3部分：每一条机器指令的地址、机器指令、机器指令所对应的汇编指令

T命令可以执行一条或多条指令，简单的使用T命令，可以执行CS：IP指向的指令
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor95j1161j30ht04ft8w.jpg)

若要用T命令控制CPU执行我们写到1000:0的指令，必须先让CS：IP指向1000:0
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor95rhjc9j30ht04mwel.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9610yqlj30ht0773yu.jpg)

5）用Debug的A命令以汇编指令的形式在内存中写入机器指令
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor96bstguj30ht051dfy.jpg)

简单的使用A命令，可以从一个预设的地址开始输入指令