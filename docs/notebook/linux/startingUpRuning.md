# 设置开机运行

## 设置synergy客户端开机启动

在`应用中心`搜索: `启动应用程序`

点击添加, 名称随意填写, 如`synergy`

命令填写

    synergyc 主机IP

将`主机IP`替换为自己服务端的IP

并在 `系统设置>用户设置` 中点击解锁, 打开自动登录开关, 否则启动输入密码后才能启动`synergy`

## 设置开机screen后台运行任务

建立一个脚本, 任意命名, 如 `screenStart.sh`

```bash
screen -S `name` -dm `run app`
```

`name` 填写后台运行标识的名字, `run app` 写自己需要运行的应用

将`bash screenStart.sh`添加到`启动应用程序`中,就可以在开机运行后台任务了

> 如建立一个后台http服务
> ```bash
> cd ~/www/
> screen -S HTTPServer -dm python -m SimpleHTTPServer
> ```
> 将在`~/www/`目录下启动一个http服务
> 使用`screen -ls`可以看到存在`HTTPServer`的后台运行服务

!!! note
    screen的具体操作请参见screen相关文档