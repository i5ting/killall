killall 
=============

a npm for kill -9 all processes


以前每次都这样杀掉所有进程

	ps -ef|grep pm2|awk '{print $2}'|xargs kill -9
	
写起来比较麻烦，于是写了`killall`这个cli工具，其实我只要输入进程名称就可以杀掉所有相关进程

## 安装

	sudo npm install -g killall

## 用法

	killall pm2
	killall node

## 测试

当前目录启动

	gulp
	
然后随便执行

	killall gulp
	
如果发现gulp中断，即表示杀死进程成功。