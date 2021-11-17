原因：

1. Ubuntu server虚拟机界面实在是不如Mac终端好操作
2. Linux下的命令与UNIX很多不一样，无法直接在macOS下学习Linux

步骤：

1. Ubuntu系统默认安装了openssh-client，但没有安装openssh-server，
先检查一下(ps -e | grep ssh)

2. 安装openssh-server：sudo apt-get install openssh-server

3. 如果出现sshd，代表安装成功【sudo /etc/init.d/ssh start启动服务】

4. ifconfig -a查看IP地址

5. ssh 用户名@IP地址 
