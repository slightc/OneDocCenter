# 部署Gitlab

[Gitlab官方推荐文档](https://about.gitlab.com/install/#ubuntu)

## 1. 安装和配置必要的依赖

    :::shell
    sudo apt-get update
    sudo apt-get install -y curl openssh-server ca-certificates

安装Postfix用于发送通知邮件. 如果想要使用其他方法发送邮件, 可以跳过这一步, 在安装完Gitlab后, [配置外部SMTP服务器](https://docs.gitlab.com/omnibus/settings/smtp.html)

    :::shell
    sudo apt-get install -y postfix

在Postfix的安装过程中,可能出现配置界面.选择 `Internet Site` 回车确定.
使用服务器外置的DNS作为 `mail name`, 并回车确定.
如果出现额外的窗口, 直接使用默认值, 回车确定.

## 2. 下载GitLab安装文件并安装

下载GitLab安装文件

    curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash

安装GitLab, 将`http://gitlab.example.com`改为自己可访问的链接

    sudo EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ee