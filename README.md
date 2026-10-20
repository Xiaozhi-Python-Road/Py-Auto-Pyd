# Py Auto Pyd

## This is a fully automatic Py to Pyd conversion tool written based on Python Batch. We have encapsulated a minimalist interface for users to call up conveniently!

## Now let's start introducing these tools! Start

### Prepare the environment

### I. Tool Compiler

  We currently support all interpreters for Python version 3.8 and above. However, due to a serious defect, we are unable to support the newly released free thread-stable ABI of the Python 3.15.0 series without CIL. We have submitted a report on this issue. For more details, please visit  

[The detailed feedback issue page](https://github.com/python/cpython/issues/159457)

### Ii. System Platform：

Supports Windows 10 22H2 or Windows 11 25H2 and above systems  

### Iii. Toolset Environment：

### We support the Visual Studio C Build Tools/MinGW compiler. We complete the external completion pyd based on batch processing and can try it out of the box. Currently, cross-platform support is not supported. We are very sorry. Please forgive us because we have no experience with mac and Linux systems!  

We have completed the environment variable. The generation tool will support generating setup.py, so you don't need to write the code by hand. However, it should be noted that we currently only support it```MSVC(2019 installer(14.29v142)+MSVC（2022 installer 14.44v143(The MSVC142 working set needs to be selected)```However, there are also some special circumstances that you need to pay attention to

### Iv. Compiler Environment：

MSVC：To facilitate a statement: Without the Windows platform and MSVC, there would be no Windows version of CPython. Since version 3.5, the official version designated by MSVC has been used for compilation. You can compile your python interpreter within the range of MSVC we support

MinGW：GCC, also known as MinGW, was migrated from Linux to Windows. However, it has a drawback: it only supports interpreter versions 3.12 and above, and cannot compile interpreters 3.11 and below; otherwise, undefined errors for variables such as 401 and 407 will be thrown! But you can switch to the officially recommended MSVC

## Alright, my introduction is over. Now you can read the main text：

## The directory structure is as follows：
![directory structure;bibliographic structure](./resources/directory-struct.png)

The most convenient part is that this tool encapsulates all the structures. Users only need to call them up, without having to write a single parameter command or code to achieve it! For setup.py, we have two sets of compiler generation tools to complete the conversion of py to pyd!
![generating tools](./resources/build_tools.png)

However, for libraries such as compilation, installation, and uninstallation, they are all handled here，

Currently, the compiler installation library only supports domestic mirror sites. If you are a foreign user, you can execute it manually``` pip install cython setuptools psutil```
![Compiler_msvc](./resources/Compiler_msvc.png)

![Interpreter query](./resources/CPython_Version_Check.png)

![Looking for MSVC](./resources/vswhere.png)

![result](./resources/jieguo.png)

![result](./resources/jieguo2.png)
Compiling pyd is this simple. If you also need this fully automatic conversion tool, you are welcome to submit your questions

# When submitting questions, it is necessary to clearly state the reasons for the application. The rest can be customized and await review

现场编译日志
```
**********************************************************************
** Visual Studio 2019 Developer Command Prompt v16.0
** Copyright (c) 2021 Microsoft Corporation
**********************************************************************
[vcvarsall.bat] Environment initialized for: 'x64'
Python版本确认 - 小智Python之路出品
使用说明(如果解释器路径忘记，请使用目录下CPthon_Version.exe):
1、输入 'python': 使用环境变量中的Python执行脚本
2、输入路径: 使用指定路径的python.exe (路径必须存在且含python.exe/python3.15t.exe)
3、输入 'exit': 退出程序
4、新版本支持python3.15无abi3t-GIL
------------------------------------------------------------

请输入(python/路径/exit): D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\python.exe
使用路径Python: D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\python.exe，执行编译！
✅ Python版本: 3.13.7 (符合要求 >= 3.8.0)，执行编译！

✅ 版本检测通过，开始执行编译...
Compiling scripts_msvc/test.py because it changed.
Compiling scripts_msvc/test1.py because it changed.
Compiling scripts_msvc/test2.py because it changed.
Compiling scripts_msvc/test3.py because it changed.
Compiling scripts_msvc/test4.py because it changed.
Compiling scripts_msvc/test5.py because it changed.
[1/6] Cythonizing scripts_msvc/test.py
[2/6] Cythonizing scripts_msvc/test1.py
[3/6] Cythonizing scripts_msvc/test2.py
[4/6] Cythonizing scripts_msvc/test3.py
[5/6] Cythonizing scripts_msvc/test4.py
[6/6] Cythonizing scripts_msvc/test5.py
running build_ext
building 'test' extension
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\cl.exe /c /nologo /O2 /W3 /GL /DNDEBUG /MD -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\include -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\Include -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\cppwinrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\shared" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\ucrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\um" -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include /Tcscripts_msvc/test.c /Fobuild\temp.win-amd64-cpython-313\Release\scripts_msvc\test.obj
test.c
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\libs /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1 /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\PCbuild\amd64 /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\um\x64" /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\ucrt" "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\um" /EXPORT:PyInit_test build\temp.win-amd64-cpython-313\Release\scripts_msvc\test.obj /OUT:build\lib.win-amd64-cpython-313\test.pyd /IMPLIB:build\temp.win-amd64-cpython-313\Release\scripts_msvc\test.lib
  正在创建库 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test.lib 和对象 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test.exp
正在生成代码
已完成代码的生成
✅ 编译成功，已归档到 build_out: test.pyd
building 'test1' extension
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\cl.exe /c /nologo /O2 /W3 /GL /DNDEBUG /MD -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\include -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\Include -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\cppwinrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\shared" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\ucrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\um" -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include /Tcscripts_msvc/test1.c /Fobuild\temp.win-amd64-cpython-313\Release\scripts_msvc\test1.obj
test1.c
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\libs /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1 /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\PCbuild\amd64 /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\um\x64" /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\ucrt" "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\um" /EXPORT:PyInit_test1 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test1.obj /OUT:build\lib.win-amd64-cpython-313\test1.pyd /IMPLIB:build\temp.win-amd64-cpython-313\Release\scripts_msvc\test1.lib
  正在创建库 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test1.lib 和对象 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test1.exp
正在生成代码
已完成代码的生成
✅ 编译成功，已归档到 build_out: test1.pyd
building 'test2' extension
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\cl.exe /c /nologo /O2 /W3 /GL /DNDEBUG /MD -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\include -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\Include -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\cppwinrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\shared" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\ucrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\um" -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include /Tcscripts_msvc/test2.c /Fobuild\temp.win-amd64-cpython-313\Release\scripts_msvc\test2.obj
test2.c
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\libs /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1 /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\PCbuild\amd64 /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\um\x64" /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\ucrt" "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\um" /EXPORT:PyInit_test2 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test2.obj /OUT:build\lib.win-amd64-cpython-313\test2.pyd /IMPLIB:build\temp.win-amd64-cpython-313\Release\scripts_msvc\test2.lib
  正在创建库 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test2.lib 和对象 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test2.exp
正在生成代码
已完成代码的生成
✅ 编译成功，已归档到 build_out: test2.pyd
building 'test3' extension
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\cl.exe /c /nologo /O2 /W3 /GL /DNDEBUG /MD -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\include -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\Include -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\cppwinrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\shared" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\ucrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\um" -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include /Tcscripts_msvc/test3.c /Fobuild\temp.win-amd64-cpython-313\Release\scripts_msvc\test3.obj
test3.c
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\libs /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1 /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\PCbuild\amd64 /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\um\x64" /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\ucrt" "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\um" /EXPORT:PyInit_test3 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test3.obj /OUT:build\lib.win-amd64-cpython-313\test3.pyd /IMPLIB:build\temp.win-amd64-cpython-313\Release\scripts_msvc\test3.lib
  正在创建库 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test3.lib 和对象 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test3.exp
正在生成代码
已完成代码的生成
✅ 编译成功，已归档到 build_out: test3.pyd
building 'test4' extension
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\cl.exe /c /nologo /O2 /W3 /GL /DNDEBUG /MD -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\include -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\Include -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\cppwinrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\shared" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\ucrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\um" -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include /Tcscripts_msvc/test4.c /Fobuild\temp.win-amd64-cpython-313\Release\scripts_msvc\test4.obj
test4.c
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\libs /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1 /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\PCbuild\amd64 /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\um\x64" /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\ucrt" "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\um" /EXPORT:PyInit_test4 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test4.obj /OUT:build\lib.win-amd64-cpython-313\test4.pyd /IMPLIB:build\temp.win-amd64-cpython-313\Release\scripts_msvc\test4.lib
  正在创建库 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test4.lib 和对象 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test4.exp
正在生成代码
已完成代码的生成
✅ 编译成功，已归档到 build_out: test4.pyd
building 'test5' extension
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\cl.exe /c /nologo /O2 /W3 /GL /DNDEBUG /MD -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\include -ID:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\Include -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\winrt" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.28000.0\cppwinrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\shared" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\ucrt" "-IC:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Include\um" -ID:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\include /Tcscripts_msvc/test5.c /Fobuild\temp.win-amd64-cpython-313\Release\scripts_msvc\test5.obj
test5.c
D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\bin\HostX64\x64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\libs /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1 /LIBPATH:D:\SOFTWARE\sde\python\python_ccompiler\Python-3.13.7-pip26.2.1\PCbuild\amd64 /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.28000.0\um\x64" /LIBPATH:D:\SOFTWARE\sde\msvc\product\VC\Tools\MSVC\14.29.30133\lib\x64 "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\ucrt" "/LIBPATH:C:\msvc_sdk\Windows SDK 10.0.28000.2705_x64\Lib\um" /EXPORT:PyInit_test5 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test5.obj /OUT:build\lib.win-amd64-cpython-313\test5.pyd /IMPLIB:build\temp.win-amd64-cpython-313\Release\scripts_msvc\test5.lib
  正在创建库 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test5.lib 和对象 build\temp.win-amd64-cpython-313\Release\scripts_msvc\test5.exp
正在生成代码
已完成代码的生成
✅ 编译成功，已归档到 build_out: test5.pyd
正在清除.c中间文件，请稍等......
正在清除build文件，请稍等......
✅ 编译完成！成功编译 6 个文件

E:\PySimle C++_G++ Build Tools\Compiler_Tools\MSVC>
```

