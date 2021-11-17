1. pwd(打印工作目录)：显示当前工作目录（第一次登录系统时或是启动终端仿真器会话时，当前工作目录被设置成主目录，每个用户账号都有一个主目录，作为普通用户操作时，这是唯一一个允许用户写文件的地方）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3ci6pionj308b014748.jpg)

2. 
ls：列出当前工作目录的文件和目录
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliywyej7aj30fb01fq2s.jpg)

通过ls命令可以查看目录内容，确定各种重要文件和目录的属性

ls 指定目录：列出指定要显示的目录
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyxa2amij30jr00zweb.jpg)

ls ~ /usr：列出用户主目录（由符号波浪线表示）和/usr目录的内容
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyxjeh5dj30jr030749.jpg)

ls -l：将输出以长格式显示
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyxs6llzj30jr0580t6.jpg)

选项和参数：通常，命令后面跟有一个或多个选项，带有不同选项的命令其功能也不一样；此外，命令后面还会跟有一个或多个参数，这些参数是命令作用的对象【command -options arguments】

大部分命令使用的选项是在单个字符前加上连字符，如-l，但是很多命令，包括GNU项目里的命令，也支持在单字前加两个连字符的长选项，而且很多命令也允许多个短选项串在一起使用

ls命令包含了两个选项，l选项产生长格式输出，而t选项则表示以文件修改时间的先后将结果进行排序，加上长选项—reverse，则结果会以相反的顺序输出
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyy74i5uj30jr07hwf8.jpg)

ls命令的常用选项
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyyo3wyoj30b405kq39.jpg)

下面的例子来自于Ubuntu系统：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyywb97tj30b403574i.jpg)
ls长列表字段：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyz85s98j30bb02kdfx.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyzg9xhjj30ax030t8q.jpg)

3. 
cd 目标工作目录的路径名：改变工作目录（即在文件系统树的位置）

路径名指的是沿着分枝到达目标目录的路由，路径名分为两种：绝对路径名和相对路径名

绝对路径名：从根目录开始，其后紧接着一个又一个文件树分支，直到到达目标目录或文件

/usr/bin:大多数系统程序都安装在这个目录里【根目录(在路径名中用前导斜杠来表示)中有一个目录是usr,该目录包含一个bin目录】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliyzq9lisj30gv09bq3b.jpg)

相对路径名：从工作目录开始，通常使用一些特殊符号来表示文件系统树中的相对位置（“.” ”..”）
“.”代表当前工作目录
“..”代表当前工作目录的父目录

我们希望把工作目录改变成/usr/bin的父目录/usr
1）绝对路径名
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz055iztj303202pwea.jpg)
2）相对路径名
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz0xhmuqj303202p3yb.jpg)

也可以把工作目录从/usr变到/usr/bin
1）绝对路径名
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz1caukmj304902pjr7.jpg)
2）相对路径名
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz1mjwjaj304902pglf.jpg)

几乎在所有的情况下都可以省略“./”，因为它是隐含的，一般而言，如果没有指定路径名，则默认为工作目录

cd的一些快捷方式：
1）cd：将当前工作目录改变为主目录
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz1vo4phj30490260sj.jpg)
2）cd -:将工作目录改变成先前的工作目录
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz24ja80j30490280sj.jpg)
3）cd ~username：将工作目录改变为username的主目录
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3d90h274j30ax03et8y.jpg)

4. 
file filename：确定文件的类型
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz2fc2haj30ax01ewee.jpg)

5. 
less filename：查看文本文件的内容，Q键退出less程序
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz2o610oj30jo0daaal.jpg)

less程序最常使用的键盘命令：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz2vyg6kj306e02hwed.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz362t6sj30aw03a74a.jpg)

6. 符号链接：

在浏览过程中，我们可能会看到带有如下条目的目录信息
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz3gvurkj30b700f743.jpg)

该条目信息的第一个字母是l，而且看起来像是有两个文件名，这种特殊的文件叫做符号链接（又叫软链接或symlink）

假设，一个程序需要使用包含foo文件中的一个共享资源，但foo版本变化很频繁，这样，在文件名中包含版本号会是一个好主意，因此管理员或其他相关方就能够看到安装了foo的哪个版本，这就出现了一个问题，如果改变了共享资源的名称，就必须跟踪每个可能使用了该共享资源的程序，并且当安装了该资源新的版本后，都要让使用它的程序去寻找新的资源名

假设foo的安装版本是2.6，他的文件名是foo-2.6，然后创建一个符号链接foo指向foo-2.6，这意味着，当一个程序打开foo文件时，它实际上打开的是文件foo-2.6.这样一来皆大欢喜，依赖foo文件的程序能够找到它，并且也能看到实际安装的版本。当需要升级到foo-2.7时，只需将该文件添加到系统里，删除符号链接文件foo，创建一个指向新版本的符号链接即可，这不仅解决了版本升级的问题，也可以将两种版本都保存在机器里。假如foo-2.7存在一个程序错误需要切换到旧的版本，同样，只需要删除指向新版本的符号链接，重新创建指向旧版本的符号链接即可

硬链接：默认情况下，每个文件有一个硬链接，该硬链接会给文件起名字。当创建一个硬链接的时候，也为这个文件创建了一个额外的目录条目
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz3ymcjfj30bd01ygli.jpg)

硬链接和文件本身没有什么区别，与包含符号链接的目录列表不同，包含硬链接的目录列表没有特别的链接指示说明。当硬链接被删除时，只是删除了这个链接，但是文件本身的内容依然存在（也就是说，该空间没有释放），除非该文件的所有链接都被删除了

ln file link：创建硬链接

ln -s item link:创建符号链接，这里的item可以是文件也可以是目录

符号链接是通过创建一个特殊类型的文件来起作用的，该文件包含了指向引用文件或目录的文本指针
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz3p41z6j30bd02mt8w.jpg)

7. 由于shell需要经常使用文件名，因此它提供了一些特殊字符来帮助你快速指定一组文件名，这些特殊字符称为通配符，通配符（也叫文件名替换）允许用户依据字符模式选择文件名
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz5f1vvwj30b707bmxh.jpg)
通配符的使用使得为文件名构建复杂的筛选标准成为可能：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz5oxz1nj30b701hmx1.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz5vrasqj30b704eq34.jpg)

8. 
mkdir dir1：创建单个dir1目录

mkdir dir1 dir2 dir3：创建3个目录

9. 
cp：复制文件和目录
cp item1 item2：将单个文件或目录item1复制到文件或目录item2中
cp item1 . :将item1复制到当前目录
cp item… directory：将多个项目（文件或目录）复制进一个目录中

需要注意的是，在没有任何警告的情况下，cp命令会覆盖第一次的复制内容（命令一样的情况下）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz6agmv7j30b704pt90.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz6ixst5j30b703wmxe.jpg)

10. 
mv：文件移动和文件重命名（在这两种情况下，完成操作后，原来的文件名将不存在）

mv item1 item2:将文件（或目录）item1移动（或重命名）为item2
mv item… directory：将一个或多个条目从一个目录移动到另一个目录下
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz6s48b9j30b706rjrx.jpg)

11. 
rm item… ：移除（删除）文件和目录
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz71tsn6j30b707wt9k.jpg)

![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz79k27mj30b703q74e.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliz7oyenvj30b703fdfv.jpg)

- - - -

（1）与Windows相同，类UNIX操作系统（Linux）也是以称之为分层目录结构的方式来组织文件的，文件系统的第一个目录叫做根目录，它包含了文件和子目录，子目录里包含了更多的文件和子目录，依此类推

（2）在Windows系统中，每个存储设备都有一个独立的文件系统树。而在类UNIX系统中，无论多少驱动器或存储设备与计算机相连，通常只有一个文件系统树。根据系统管理员的设置，存储设备将会连接（挂载）到文件系统树的不同位置，系统管理员要负责系统的维护 

（3）树通常是倒立显示的，顶部是根目录，依次向下排列的是子目录 
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliysz8hrej306n057wef.jpg)

（4）以“.”字符开头的文件名是隐藏的，这仅说明ls不会列出这些文件，除非输入ls -a,在创建用户账号时，主目录里会放置一些隐藏文件，用来配置账号信息，此外，一些应用程序也会将它们的配置文件和设置文件以隐藏文件的形式放在主目录下面 
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3ddkhsjfj30dg055dgo.jpg)

（5）与UNIX一样，在Linux中，文件名与命令是区分大小写的 

（6）Linux没有文件扩展名的概念，我们可以按照自己的喜好随意给文件命名，文件的内容或用途由其他方式来决定 

（7）Linux支持长文件名，但是在创建文件名的过程中，仅句号、连字符和下划线是可以使用的，文件名中不要嵌入空格，可以使用下划线 

（8）在Linux系统中找到的目录：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliytnrpmfj30b70dmgn1.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gliytw7npwj30b708p3zd.jpg)

- - - -

实战演练：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3ffnt6oqj30eu08yt9e.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3ffwsikij30u010adl3.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3fg3i45pj30tz121wk1.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3fgar2u8j30tu11z44m.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3fgqh4uej30u011qwkc.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gm3fgx369gj30qj0vzq9f.jpg)
