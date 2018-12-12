# 个人文档中心

文档使用**markdown**编辑,使用**mkdocs**框架,**material**主题

## 文档编辑环境

环境需要安装python,mkdocs参考文档见[链接](https://www.mkdocs.org/#getting-started),
默认python环境已经安装(python2与python都可以)

环境使用如下命令安装

Linux下使用命令

```bash
pip install mkdocs --user
pip install mkdocs-material --user
pip install pygments --user
```

Windows下使用命令

```cmd
pip install mkdocs
pip install mkdocs-material
pip install pygments
```

如果python的markdown版本过低,使用下面命令升级markdown

Linux

```bash
pip install --upgrade markdown --user
```

Windows

```cms
pip install --upgrade markdown
```

## 文档预览

在此目录下执行下面命令

```bash
mkdocs serve
```

将在本地`8000`端口开启网页服务,通过浏览器就可以访问文档,
源文档文件修改保存后预览将实时更新

## 文档发布

使用

```bash
mkdocs gh-deploy
```

文档将打包发布在page页面