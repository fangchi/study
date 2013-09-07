vagrant
==========================
安装虚拟机
$ vagrant box add {你想要的Box名稱} {下載網址}

生成配置文件
$vagrant init 

配置VagrantFile(可以不修改)

如果修改了
$vagrant reload

如果没修改
$vagrant up

knife
Knife是Opscode推出的一套command line的Chef管理工具，你可以在你的workingstation的機器使用Knife來管理VPS上的Chef，你甚至不用手動去幫機器安裝Chef-Solo
==========================
执行安装命令
$ sudo gem install knife-solo

这个会在你本机生成一个基础目录 通常这个目录里面 就是配置  会使用git 同步保存的 .表示在当前目录下生成
$knife solo init .  

只运行一次 这个会在虚拟机自动安装chef 其实就是会上传一个install.sh文件到虚拟机里 然后在虚拟机执行 这个install.sh就是安装chef的脚本
$knife solo prepare vagrant@ip 

....
配置相应的命令

密码是vagrant 这个就是运行那些安装脚本的  其实是把之前生成的目录下的文件上传到虚拟机 然后执行
$knife solo cook vagrant@ip

以上两条命令的合并
$knife solo bootstrap vagrant@ip

查看
$knife solo -help

other
===========================
安装Tree命令
$ brew install tree
SSH连接
$ ssh user@ip