1. 在任意输入框中按option+shift+K组合键会显示苹果logo
2. 文本编辑中按Fn+Delete键可向后删除内容
3. Finder+菜单栏中的前往+一直按住option，打开资源库
4. 终端输入sudo spctl —master-disable命令打开【安全性与隐私】中的【任何来源】
5. 隐藏和恢复桌面文件： 
- 隐藏桌面文件：defaults write com.apple.finder CreateDesktop -bool false; 
  killall Finder 
- 恢复显示桌面文件：defaults write com.apple.finder CreateDesktop -bool true; 
  killall Finder
6. 快速调用emoji表情：control+command+空格
7. CheatSheet:长按command键可显示当前应用所有的快捷键
8. 调整launchpad图标大小： 
   - 改行数：defaults write com.apple.dock springboard-rows -int 10 
   - 改列数：defaults write com.apple.dock springboard-columns int 7 
   - killall Dock 

恢复系统默认： 

- defaults write com.apple.dock springboard-rows Default 
- defaults write com.apple.dock springboard-columns Default 
- killall Dock

9. 移动文件：打开源文件夹和目标文件夹，拖拽源文件到目标文件夹 
拷贝文件：按住option，拖拽源文件到目标文件夹 
10. 全屏截图：command+shift+3 
截取部分屏幕：command+shift+4
11. 回到桌面：command+F3
