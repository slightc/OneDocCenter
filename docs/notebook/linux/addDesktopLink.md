# 添加应用/脚本桌面快捷方式

> 使用ubuntu18系统

在桌面新建一个 `xxx.desktop` 文件

    #!shell
    cd ~/Desktop
    nano xxx.desktop

在 `xxx.desktop` 中写入

``` properties tab="脚本"
[Desktop Entry]

Name = 显示的名字
Exec = bash /运行脚本的完整路径
Icon = /图标的完整路径
Comment = 鼠标放上显示的文字
Encoding = UTF-8
Type = Application
```

``` properties tab="可执行文件"
[Desktop Entry]

Name = 显示的名字
Exec = /可执行文件的完整路径
Icon = /图标的完整路径
Comment = 鼠标放上显示的文字
Encoding = UTF-8
Type = Application
```

按照自己需要修改 `Name` `Exec` `Icon` `Comment`

点击运行将弹出是否信任快捷方式, 选择信任, 完成快捷方式建立