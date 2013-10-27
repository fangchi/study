**vagrant 学习**
========================
vargant是什么?
----------------
Vagrant是一个基于Ruby的工具，用于创建和部署虚拟化开发环境。它使用（但不仅仅使用）Oracle的开源VirtualBox虚拟化系统，使用 Chef创建自动化虚拟环境。

软件地址：
----------------
- [1.virtualBox下载地址](http://download.virtualbox.org/virtualbox/4.2.18/VirtualBox-4.2.18-88780-OSX.dmg) （OSX）

- [2.vagrant 下载地址](http://downloads.vagrantup.com/)

- [3.参考网址](http://docs.vagrantup.com/v2/getting-started/index.html)

环境搭建步骤
----------------
`$ vagrant up --provider=vmware_fusion` 设置虚拟机依赖的组件为vmware

`$ sudo launchctl load /Library/LaunchDaemons/org.virtualbox.startup.plist` 当OS为OSX 10.9的时候 需要首先载入启动参数

`$ vagrant init precise32 http://files.vagrantup.com/precise32.box` 初始化一个基于Ubuntu 12.04 LTS 32-bit 操作系统 执行完该命令之后会在当前文件夹创建一个Vagrantfile的文件，而precise32.box相当于一个虚拟机的**镜像（Image）**
- Vagrantfile 是一个定义虚拟机的配置文件（包含名称，镜像地址，网络等），也就是说如果需要复制一个开发环境 ，仅仅需要一个VagrantFile这样的配置文件就可以通过vagrant up命令构建一个一模一样的虚拟机
- Vagrantfile 的语法模式是Ruby，但是其实基本不需要十分了解Ruby的语法，大部分是一些变量的赋值
- vagrant 查找配置文件的顺序为
`/home/mitchellh/projects/foo/Vagrantfile`

`/home/mitchellh/projects/Vagrantfile`

`/home/mitchellh/Vagrantfile`

`/home/Vagrantfile`

`/Vagrantfile`

- 常用的配置项目

[参考网址](http://docs.vagrantup.com/v2/vagrantfile/machine_settings.html)

config.vm.provider 虚拟机实现（VirtaulBox,VMWare）

`$ vagrant up` 启动虚拟机

`$ vagrant reload` 重新加载虚拟机配置文件并重启

`$ vagrant exit` 退出登录

`$ vagrant destroy` 销毁所有虚拟机

`$ vagrant box list` 列举虚拟机

[通篇教学] (http://gogojimmy.net/2013/05/26/vagrant-tutorial/)
