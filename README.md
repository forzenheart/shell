# shell
##编程项目：开发一个shell程序
###shell或者命令行解释器是操作系统中最基本的用户接口。
###设计一个简单的shell程myshell，它具有以下属性：
####1.这个shell程序必须支持以下内部命令： 
* a) cd < directory >——把当前默认目录改变为<directory>.如果没有<directory>参数，则显示当前目录。如果该目录不存在，则会出现合适的错误信息。这个命令也可以改变PWD环境变量。
* b) clr ——清屏
* c) dir < directory >——列出目录<directory>的内容。
* d) environ——列出所以的环境变量
* e) echo < coommnet >——在屏幕上显示<coommnet>并换行(多个空格和制表符可能被缩减为一个空格).
* f) help——显示用户手册，并且使用more命令过滤。
* g) pause——停止shell操作直到按下回车键。
* h) quit——退出shell。
* i) shell的环境变量应该包含shell=<pathname>/myshell.其中<pathname>/myshellshell是可执行程序shell的完整路径（不是你的目录下的硬连线路径，而是它的执行路径）.

####2.其他的命令行输入被解释为程序调用，shell创建并执行这个程序，作为自己的子进程。程序的执行环境包含以下条目:
		parent=<pathname>/myshell,其中<pahtname>/myshell已经在1.i里面解释过了。

####3.shell必须能够从文件中提取命令行输入，例如shell使用以下命令行被调用：
		myshell batchfile
这个批处理文件包含一组命令集，当到达文件结尾时shell退出。很明显，如果shell被调用时没有参数，它会在屏幕上显示提示符请求用户输入。

####4.shell必须支持I/O重定向，stdin和stdout。或者其中之一。例如命令行为:
		programname arg1 arg2 < inputfile > outputfile 
使用arg1和arg2执行程序programname，输入流文件被替换为inputfile，输出流文件被替换为outputfile.
stdout重定向应该支持以下内部命令：dir, environ, echo, &help.
使用输出重定向时，如果重定向符是 >, 则创建输出文件，如果存在就覆盖之。如果重定向字符为>>，也会创建文件，如果存在则添加到文件尾。

####5.shell必须支持后台程序执行.
如果在命令行后添加&字符，在加载完程序后需要立刻返回命令行提示符。
####6.命令行提示符必须包含当前路径。
提示，你可以假设所有命令行参数(包括重定向字符<, >, >>和后台执行字符&)和其他命令行参数用空白空间分开，空白空间可以为一个或多个空格或制表符。

##项目要求：

####1.设计一个简单的命令行shell,满足上面的要求并且在指定的UNIX平台上执行。
####2.写一个关于如何使用shell的简单的用户手册，用户手册应该包含足够的细节以方便UNIX初学者使用。
例如，你应该解释I/O重定向，程序环境和后台程序执行。用户手册必须命名为readme,必须是一个标准文本编辑器可以打开的简单文本文档。举一个描述的类型和升读的例子。你应该看以下csh和tcsh的在线帮助(man csh, man tcsh)这两个shell显然比你的shell有更多的功能，你的用户手册没必要做这么大。不包括编译指示——文件列表或源码，我们可以从你提交的其他文件中找出来。这应该是操作员手册而非程序元手册。
####3.源码必须有很详细的注释，并且有很好的组织结构以方便别人阅读和维护。结构和注释好的程序更加易于理解，并且可以保证批改你作业的人不用很费劲地去读你的代码。
####4.在截止期之前，要提供很详细的提交过程。
####5.提交内容为源码文件，包括文件，makefile(全部小写)和readme(全部小写)文件。
####6.makefile(全部小写)必须产生二进制文件myshell(全部小写)。一个makefile的例子如下:
	# Joe Citizen, s1234567 - Operating System Project 1
	# CompLab/01 tutor: Fred Bloggs
	myshell: mysheel.c utility.c -o myshell
	gcc -Wall myshell.c utility.c -o myshell
提示：上面makefile的第４行必须以制表符开始。
####7.根据上面提供的实例，提交的目录应该包含以下文件:
	makefile
	myshell.c
	utility.c
	myshell.h
	readme
