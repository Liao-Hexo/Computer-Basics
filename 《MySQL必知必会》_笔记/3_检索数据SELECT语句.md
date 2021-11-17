检索数据【SELECT语句】：


检索单个列：

从db表中检索一个名为Host的列：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort6c7xeij306303a74d.jpg)
从db表中检索多个列：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort6kg84nj30ab03pglt.jpg)
从db表中检索所有列：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort6tsbinj30ev0d4dgj.jpg)

检索不同的行？？
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort72pvf9j30ai0dljtw.jpg)
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort79ppwjj30ai059myt.jpg)

限制结果：
LIMIT 1；【指示MySQL返回不多于1行】
LIMIT 1，2；【第一个数为开始位置，第二个数为要检索的行数】
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort7jl4ayj308b0a6aal.jpg)
1）所以，带一个值的LIMIT总是从第一行开始，给出的数为返回的行数。带两个值的LIMIT可以指定从行号为第一个值的位置开始
2）检索出来的第一行为行0而不是行1，因此，LIMIT 1，1将检索出第二行而不是第一行
3）LIMIT中指定要检索的行数为检索的最大行数，如果没有足够的行（例如，给出LIMIT 10，5，但只有13行），MySQL将只返回它能返回的那么多行


使用完全限定的表名：
![](https://tva1.sinaimg.cn/large/008eGmZEly1gort7w68sij308b03w0sv.jpg)
