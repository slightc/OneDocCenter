# 系统配置

## 不显示检查系统应用错误

打开`/etc/default/apport`

将enabled修改为0

```shell
enabled=0
```

将不再在开机时弹出`系统应用错误`

## 设置开机启动项菜单时间

修改配置文件`/etc/default/grub`,修改前如下

```shell
GRUB_DEFAULT=0
GRUB_HIDDEN_TIMEOUT=0
GRUB_HIDDEN_TIMEOUT_QUIET=true
GRUB_TIMEOUT=10
GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""
```

使用`sudo nano`打开文件

```shell
sudo nano /etc/default/grub
```

修改`GRUB_TIMEOUT`为自己要显示启动项菜单时间,并注释`GRUB_HIDDEN_TIMEOUT`和`GRUB_CMDLINE_LINUX_DEFAULT`,修改后如下

```shell
GRUB_DEFAULT=0
#GRUB_HIDDEN_TIMEOUT=0
GRUB_HIDDEN_TIMEOUT_QUIET=true
GRUB_TIMEOUT=3
GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
#GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" #可以不注释
GRUB_CMDLINE_LINUX=""
```

!!! note
    `GRUB_TIMEOUT`不能设为0,设为0将会是默认的10S

最后执行更新配置

```shell
sudo update-grub
```