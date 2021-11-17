——————————————————————————
5.1.[BX]
5.2.Loop指令
5.3.在Debug中跟踪用loop指令实现的循环程序
5.4.Debug和汇编编译器masm对指令的不同处理
5.5.loop和[bx]的联合应用
5.6.段前缀
5.7.一段安全的空间
5.8.段前缀的使用
——————————————————————————

要完整的描述一个内存单元，需要两种信息：内存单元的地址、内存单元的长度（类型）

用[0]表示一个内存单元时，0表示单元的偏移地址，段地址默认在ds中，单元的长度（类型）可以由具体指令中的其他操作对象（比如说寄存器）指出

[bx]同样也表示一个内存单元，它的偏移地址在bx中

loop：循环

用一个描述性的符号“（）”来表示一个寄存器或一个内存单元中的内容，（）中的内存单元的地址为物理地址

（）中的元素可以有3种类型：寄存器名、段寄存器名、内存单元的物理地址（一个20位数据）
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9pszkg6j309a015aa8.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9q2v7itj30c9090mz9.jpg)

约定符号idata表示常量
——————————————————

![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9qhyixyj30cl0az3zx.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9qqfny7j30ch0hiq5j.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9qydnulj30ch087ta6.jpg)

———————————————


loop指令的格式是：loop 标号
CPU执行loop指令的时候，要进行两步操作：(cx)=(cx)-1、判断cx中的值，不为零则转至标号处执行程序，如果为零则向下执行【通常，我们用loop指令来实现循环功能，cx中存放循环次数】

assume cs:code
code segment
    mov ax,2
    mov cx,11
s:
    add ax,ax
    loop s

    mov ax,4c00h
    int 21h
code ends
end
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9rb1gsqj30ch07zmyk.jpg)

1）在cx中存放循环次数
2）loop指令中的标号所标识地址要在前面
3）要循环执行的程序段，要写在标号和loop指令的中间
——————————————

在Debug中跟踪用loop指令实现的循环程序：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9rkgjpaj30cm0aa75q.jpg)

1）标号s前的指令我们已经确定在逻辑上完全正确，不想再一步一步跟踪了（g IP，直接跳转到IP值处）
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9rucjibj30ht09ldgb.jpg)

2）循环也不想再一步一步跟踪了（遇到loop，直接p）
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9s38jfwj30ht0bqmy5.jpg)

———————————————————

Debug和汇编编译器masm对指令的不同处理：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gor9sdhx36j30b109tq4i.jpg)
