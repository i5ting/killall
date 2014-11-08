killall 
=============

a npm for kill -9 all processes

[![npm version](https://badge.fury.io/js/killall.svg)](http://badge.fury.io/js/killall)

以前每次都这样杀掉所有进程

	ps -ef|grep pm2|awk '{print $2}'|xargs kill -9
	
写起来比较麻烦，于是写了`killall`这个cli工具，其实我只要输入进程名称就可以杀掉所有相关进程

其实系统内置了pgrep和pkill和killall命令的，此repo权当练习自娱自乐吧

- 已测试mac 10.9.3
- 已测试centOS 6.0

```
	~  man pgrep
	PGREP(1)                      Linux User’s Manual                     PGREP(1)



	NAME
	       pgrep, pkill - look up or signal processes based on name and other attributes


	SYNOPSIS
	       pgrep [-flvx] [-d delimiter] [-n|-o] [-P ppid,...] [-g pgrp,...]
	            [-s sid,...] [-u euid,...] [-U uid,...] [-G gid,...]
	            [-t term,...] [pattern]

	       pkill [-signal] [-fvx] [-n|-o] [-P ppid,...] [-g pgrp,...]
	            [-s sid,...] [-u euid,...] [-U uid,...] [-G gid,...]
	            [-t term,...] [pattern]


	DESCRIPTION
	       pgrep  looks  through  the  currently running processes and lists the process IDs which matches the selection criteria to stdout.  All the criteria have to
	       match.  For example,

	       pgrep -u root sshd

	       will only list the processes called sshd AND owned by root.  On the other hand,

	       pgrep -u root,daemon

	       will list the processes owned by root OR daemon.

	       pkill will send the specified signal (by default SIGTERM) to each process instead of listing them on stdout.
	~  man killall

	NAME
	       killall - kill processes by name

	SYNOPSIS
	       killall [-Z,--context pattern] [-e,--exact] [-g,--process-group] [-i,--interactive] [-q,--quiet] [-r,--regexp] [-s,--signal signal] [-u,--user user]
	       [-v,--verbose] [-w,--wait] [-I,--ignore-case] [-V,--version] [--] name ...
	       killall -l
	       killall -V,--version

	DESCRIPTION
	       killall sends a signal to all processes running any of the specified commands. If no signal name is specified, SIGTERM is sent.

	       Signals can be specified either by name (e.g. -HUP or -SIGHUP ) or by number (e.g. -1) or by option -s.

	       If the command name is not regular expression (option -r) and contains a slash (/), processes executing that particular file will be selected for  killing,
	       independent of their name.

	       killall  returns  a  zero  return code if at least one process has been killed for each listed command, or no commands were listed and at least one process
	       matched the -u and -Z search criteria. killall returns non-zero otherwise.

	       A killall process never kills itself (but may kill other killall processes).
```

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

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## 版本历史

- v1.0.4 当前正式版本
- v0.1.0 初始化版本

## 欢迎fork和反馈

- write by `i5ting` shiren1118@126.com

如有建议或意见，请在issue提问或邮件

## License

this repo is released under the [MIT
License](http://www.opensource.org/licenses/MIT).