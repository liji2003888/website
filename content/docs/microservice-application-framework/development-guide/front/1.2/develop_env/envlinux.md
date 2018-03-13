+++
title = "软件安装(Ubuntu)"
date = "2017-02-01"
draft = false
weight= 2
+++

# 软件安装

## 安装工具

- NVM
- VScode或其他代码编辑器安装
- Git

## NVM 安装

- 打开终端 输入
- `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.6/install.sh | bash`
- 如果没有curl命令，可以通过wget命令:
- `wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.6/install.sh | bash`
- 在~/.nvm, ~/.bash_profile, ~/.zshrc, ~/.profile, ~/.bashrc 其中任意一个文件中加入
- `export NVM_DIR="$HOME/.nvm"`
- `[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm`
- 这里修改~/.profile, `vim ~/.profile`, 如果没有vim, `apt-get install vim`或者直接编辑文件
![git submodule 子模块操作](./images/unvm.jpg)
- 然后输入`source ~/.profile`,通过`nvm -v`便可以看到nvm版本和相关操作
![git submodule 子模块操作](./images/unvm1.jpg)
- 通过`nvm install 6.11.4`安装node的6.11.4版本,其他版本相似
![git submodule 子模块操作](./images/nvm2.jpg)
---
详细NVM安装使用和系统权限等问题可看文档（通过其他方式进行安装）
* [NVM的github](https://github.com/creationix/nvm)
## git 安装

- 打开终端 输入 `apt-get install git` 安装git命令
## VScode或其他代码编辑器安装

1. 在 [VScode官网](https://code.visualstudio.com/Download) 下载安装
2. 在 [WebStorm官网](http://www.jetbrains.com/webstorm/) 下载安装

## 全局安装 Webpack

我们希望能够在系统的任何文件夹中使用 Webpack，使用的方式是通过 Webpack 命令来完成的，这需要我们全局安装 Webpack。这也只需要安装一次，以后每个项目就不需要重新全局安装了。

```
$ npm install webpack -g
```

成功安装之后，你应该能够在任何目录中执行 webpack 命令，如果你还没有项目的配置文件的话，应该会看到当前的 Webpack 版本和一个命令的帮助列表。

## 全局安装 Gulp

在项目中，gulp 用于监视各模块文件的变化和同步相应的文件到boot目录中。

```
$ npm install gulp -g
```

安装成功后，在终端里运行 `gulp -v` 应该可以看到gulp的版本信息。

## 全局安装 yeoman

在项目中，yeoman 用于自动生成与boot同级的模块目录和文件。

```
$ npm -g install yo
```

安装成功后，在终端里运行 `yo --version` 应该可以看到yeoman的相关信息。

## 在linux上安装python
### 直接使用apt-get进行安装
```
apt-get install python && python-pip
```
### 源代码进行安装,准备编译环境
```
yum groupinstall 'Development Tools'
yum install zlib-devel bzip2-devel openssl-devel ncurses-devel
```
### 下载python2.7代码包
```
wget https://www.python.org/ftp/python/2.7.14/Python-2.7.14.tar.xz
```
在安装包中有一个README的文件，里面有写如何安装
```
tar Jxvf Python-2.7.14.tar.xz
cd Python-2.7.14
./configure --prefix=/usr/local/python
make && make install
```
做软链接
```
ln -s /usr/local/python3/bin/python2.7 /usr/local/bin/python
```
安装成功后，如果提示：`Ignoring ensurepip failure:pip 7.1.2 requires SSL/TLS`
这是由于没有安装或升级oenssl
```
yum install openssl-devel
```
再次重复编译方案python2.7

![](./images/linuxpython.png)

提示同时成功安装pip-7.12与setuptools

做软链接
```
ln -s /usr/local/python3/bin/pip /usr/local/bin/pip
```

升级pip到最新版本
```
pip install --upgrade pip
```

## 克隆代码

可以新建一个 `hap-cloud-front` 的目录，进入到该目录下，在终端执行

```
git clone -b release-1.2.0 https://xxxx@rdc.hand-china.com/gitlab/HAPCloud/HAPCloudFront.git --recursive
```

其中 `xxxx` 是你的工号。

(确保克隆之前设置了 `git config --global user.name git config --global user.email` )

- [git submodule 子模块操作](https://git-scm.com/book/zh/v1/Git-%E5%B7%A5%E5%85%B7-%E5%AD%90%E6%A8%A1%E5%9D%97)
- [git config 配置操作](https://git-scm.com/book/zh/v1/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-%E9%85%8D%E7%BD%AE-Git)

## 运行代码

进入到项目根目录，打开终端，键入`bash boot\structure\npm.sh boot iam`。

安装依赖完成后，执行`node_modules/.bin/gulp`,如果已全局安装gulp,则可直接执行gulp

不要关闭该终端(在iam等其他模块项目中源文件发生修改时，gulp会自动检测修改并同步)，新开一个`git bash`同样在该目录下执行 `npm start` 启动项目，看到如图所示效果说明启动成功

![](./images/gulp.jpg)

![](./images/success.jpg)

提示: (可以通过 `gulp clean` 删除所有自动生成的文件,再通过 `gulp` 来重新生成，再重新启动 `npm start` ，这样可以解决有时页面未更新的状态)

## 查看效果

在浏览器中键入 `localhost:9090/`