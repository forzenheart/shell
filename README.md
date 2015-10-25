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
