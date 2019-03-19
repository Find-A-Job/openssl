# openssl
编译成.h,.lib,.dll文件
下载openssl-1.0.2r，在readme中找到对应平台的说明文件并打开，我电脑是win10，64位，所以打开的是INSTALL.W64，其中安装步骤如下：
> perl Configure VC-WIN64A
> ms\do_win64a
> nmake -f ms\ntdll.mak
> cd out32dll
> ..\ms\test
在执行上述操作之前，需要安装perl，nasm，vs2015（其他vs版本也可以），安装完成之后把perl.exe，nasm.exe,nmake.exe各自所在的路径加入环境变量。
1.打开“vs2015 x64 本机工具命令提示符”，
2.cd进入openssl-1.0.2r目录
