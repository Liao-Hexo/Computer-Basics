## Markdown介绍

Markdown是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档

Markdown编写的文档可以导出HTML、Word、图像、PDF、Epub等多种格式的文档

Markdown编写的文档后缀为.md、.markdown

macOS系统推荐使用Typora编辑器

## Markdown标题

使用`#`号可表示1～6级标题，一级标题对应一个`#`号，二级标题对应两个`#`号，以此类推

`# 一级标题`

`## 二级标题`

`### 三级标题`

`#### 四级标题`

`##### 五级标题`

`###### 六级标题`

## Markdown段落格式

### 字体

Markdown可以使用以下几种字体：

*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___

### 分隔线

可以在一行中用三个以上的星号、减号来建立一个分隔线，行内不能有其他东西

### 删除线

如果段落上的文字要添加删除线，只需要在文字的两端加上两个波浪线`~~`即可：~~删除的文本~~

### 下划线

下划线可以通过HTML的`<u>`标签来实现：<u>带下划线文本</u>

### 脚注

脚注是对文本的补充说明

[^ 注释]: 这是一款手游

王者荣耀[^ 注释]
## Markdown列表

### Markdown支持有序列表和无序列表

无序列表使用星号`*`、加号`+`或者减号`-`作为列表标记，这些标记后面要添加一个空格，然后再填写内容

* 第一项
* 第二项

+ 第一项
+ 第二项

- 第一项
- 第二项

有序列表使用数字并加上`.`号来表示

1. 第一项
2. 第二项

### 列表嵌套

列表嵌套只需在子列表中的选项前面添加四个空格即可

1. 第一项
      - 第一项嵌套的第一个元素
      - 第一项嵌套的第二个元素
2. 第二项
      - 第二项嵌套的第一个元素
      - 第二项嵌套的第二个元素

## Markdown区块

### 区块引用

Markdown区块引用是在段落开头使用`>`符号，然后后面紧跟一个空格符号

> 区块引用一
>
> 区块引用二

### 区块嵌套

另外区块也是可以嵌套的，一个`>`符号是最外层，两个`>`符号是第一层嵌套，以此类推

> 最外层
>
> > 第一层嵌套
> >
> > > 第二层嵌套

### 区块中使用列表

> 区块中使用列表
>
> 1. 第一项
> 2. 第二项
>
> - 第一项
> - 第二项

### 列表中使用区块

如果要在列表项目内放进区块，那么就需要在`>`前添加四个空格的缩进

- 第一项

  > 区块一
  >
  > 区块二

- 第二项

## Markdown代码

如果是段落上的一个函数或片段的代码可以用反引号把它包起来

`print('hello')`

### 代码区块

可以指定一种语言

```c
#include<stdio.h>
int main() {

  printf("hello");
}
```

## Markdown链接

`[链接名称](链接地址)`

`<链接地址>`

[百度](https://www.baidu.com)

<https://www.baidu.com>

### 高级链接

我们可以通过变量来设置一个链接，变量赋值在文档末尾进行

```
这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）

  [1]: http://www.google.com/
  [runoob]: http://www.runoob.com/
```

这个链接用 1 作为网址变量 [Google][1]
这个链接用 runoob 作为网址变量 [Runoob][runoob]
然后在文档的结尾为变量赋值（网址）

[1]:  http://www.google.com/
[runoob]:  http://www.runoob.com/

## Markdown图片

```
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

![alt 汽车](/Users/liaojialong/Pictures/壁纸2.jpeg "跑车")

Markdown还没办法指定图片的高度和宽度，如果需要的话，可以使用普通的<img>标签

<img src="/Users/liaojialong/Library/Application Support/typora-user-images/image-20210523195705235.png" width="25%">

## Markdown表格

Markdown制作表格使用`|`来分隔不同的单元格

`| 表头 | 表头 |`

|  表头  | 表头   |
| :----: | ------ |
| 单元格 | 单元格 |
| 单元格 | 单元格 |

## Markdown高级技巧

### 支持的HTML元素

不在Markdown涵盖范围之内的标签，都可以直接在文档里面用HTML撰写，目前支持的HTML元素有`<kbd>`、`<b>`、`<i>`、`<em>`、`<sup>`、`<sub>`、`<br>`等

使用<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Del</kbd> 重启电脑

### 转义

Markdown使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符，Markdown使用反斜杠转义特殊字符

**文本加粗**

\*\* 正常显示星号 \*\*

Markdown支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

```
\   反斜线
`   反引号
*   星号
_   下划线
{}  花括号
[]  方括号
()  小括号
#   井字号
+   加号
-   减号
.   英文句点
!   感叹号
```

### 公式

当你需要在编辑器中插入数学公式时，可以使用两个美元符`$$`包裹`TeX`或`LaTeX`格式的数学公式来实现，提交后，问答和文章页会根据需要加载`Mathjax`对数学公式进行渲染

```
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$
```

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$

