# openssl
编译成.h,.lib,.dll文件<br>
下载openssl-1.0.2r，在readme中找到对应平台的说明文件并打开，<br>
我电脑是win10，64位，所以打开的是INSTALL.W64，其中安装步骤如下：<br>
\> perl Configure VC-WIN64A<br>
\> ms\do_win64a<br>
\> nmake -f ms\ntdll.mak<br>
\> cd out32dll<br>
\> ..\ms\test<br>
在执行上述操作之前，需要安装perl，nasm，vs2015（其他vs版本也可以），<br>
安装完成之后把perl.exe，nasm.exe，nmake.exe各自所在的路径加入环境变量。<br>
1.以管理员身份打开“vs2015 x64 本机工具命令提示符”，<br>
2.cd进入openssl-1.0.2r目录<br>
3.输入命令时注意大小写，我不确定大小写是否影响最终结果，规范最好<br>
