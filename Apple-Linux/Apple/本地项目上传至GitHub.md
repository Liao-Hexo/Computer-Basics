### 首次使用

```
1. 配置SSH

   cd 项目文件夹
   git init
   ssh-keygen -t rsa -C "2668802570@qq.com"
   pbcopy < ~/.ssh/id_rsa.pub  #将ssh代码复制到剪贴板
   回到GitHub界面，将刚才生成的ssh配置到GitHub里
   ssh -T git@github.com  #验证是否添加ssh成功了

2. 开始上传代码

   git clone 仓库地址
   cd 仓库
   git add --all
   git commit -m "第1次上传"
   git push
```

### 以后使用

```
   cd 项目文件夹
   执行步骤2
```
