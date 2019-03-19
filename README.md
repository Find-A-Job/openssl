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
1.以管理员身份打开“vs2015 x64 本机工具命令提示符”，之后的命令都在此窗口执行<br>
2.cd进入openssl-1.0.2r目录<br>
3.输入命令时注意大小写，我不确定大小写是否影响最终结果，规范最好<br>
4.输入perl Configure VC-WIN64A并回车之后，会出现Configured for VC-WIN64A表示成功，其他的可能表示出错<br>
5.输入ms\do_win64a并回车,<br>
6.输入nmake -f ms\ntdll.mak并回车之后，窗口开始跑数据，需要等待几分钟，如果没有出现等待，极有可能是出错了<br>
7.后面两步是验证，进入out32dll目录，然后返回上一层目录，<br>
并执行该层目录的ms文件夹内的test程序进行测试，通过则会显示pass all test<br>
<br>
在vs项目属性里，添加h文件路径，以及lib文件路径，在文件中以#pragma comment(lib, "")方式引用lib文件（或在项目属性链接里添加*.lib文件,效果一样）<br>
openssl需要的h文件是ssl.h,需要的lib文件和dll文件是libeay32和ssleay32，<br>
其中dll文件需要拷至项目源文件目录下（也就是项目的.h,.cpp文件所在目录)<br>
<br>
如果上述中的任何一步有异常，则需要重新考虑一下问题原因<br>
1.相关程序未安装<br>
2.环境变量中未添加相关的路径<br>
3.openssl源文件下载了错误的版本<br>
4.大小写问题，或者没注意字符输错了，最好手动输入，不要复制粘贴<br>
5.未在vs的命令提示符窗口输入命令<br>
6.误操作之后在openssl文件夹内有垃圾文件干扰<br>
<br>
最后很重要的一点，欲速则不达，耐心一点，我尝试了一天，baidu了各种各种，最后静下心来总结，才完成这一步<br>
