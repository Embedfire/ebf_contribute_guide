.. vim: syntax=rst

.. highlight:: sh

sphinx的安装与使用
============================

安装sphinx
-----------

sphinx官方安装说明：
http://www.sphinx-doc.org/en/master/usage/installation.html

readthedoc官方说明：
https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html


总的来说步骤如下：

- 安装python3
- 通过python3安装sphinx包
- 根据项目要求安装项目的requirements.txt里的软件包


安装python3

windows直接到python官网下载安装

Ubuntu下使用如下指令安装：
::

    sudo apt install python3

安装sphinx
---------------
windows下使用如下指令安装：

::

    py -3 -m pip install sphinx
    #国内用户推荐使用清华源安装，使用-i指定源
    py -3 -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx

Ubuntu下使用如下指令安装

::

    python3 -m pip install sphinx
    #国内用户推荐使用清华源安装，使用-i指定源
    py -3 -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx





创建sphinx文档
----------------------

本文档已适配好支持markdown、默认的readthedoc主题等内容。
推荐直接使用本文档作为模版，修改conf.py文件的配置即可改变项目的名字、主题之类的内容。

使用时，
要先根据项目的 **requirements.txt** 安装依赖的python包。

::

    #Windows指令，推荐使用powershell运行
    py -3 -m pip install -r requirements.txt
    #Ubuntu指令
    python3 -m pip install -r  requirements.txt


创建全新的sphinx文档
----------------------
若不想使用本工程模版，可以使用如下指令创建全新的文档。

::

    sphinx-quickstart

按照提示回答问题即可。
推荐使用默认的_build目录，与vscode保持一致。
其中提示语言时可以使用这个中文代码：zh_CN

sphinx默认不支持markdown语法，要支持的话请参考本模版的conf.py文件配置。


编译
-------------------------
如果使用了vscode的rst插件，可以直接，保存rst文件后它会自动编译并可预览。

到文档源码所在的makefile目录：

::

    #在文档的makefile目录下执行

    #Windows指令
    make.bat  html
    #Ubuntu指令
    make html

在设定的build或_build的html目录下会生成静态的html文件。可直接使用这些静态的html文件制作网站。




使用python服务器预览
------------------------------
vscode插件预览有时不够完整，可以在本地开启一个python服务器来预览。
进入到生成的_build/html目录，运行如下指令：

::

    #在生成的html目录执行如下指令
    #Windows
    py -3 -m http.server  8000

    #Ubuntu
    python3 -m http.server 8000

运行指令后，在浏览器中打开 http://localhost:8000 即可查看生成的静态网页。


清除编译输出
-------------------------

有时html文件不会完全达到我们修改rst后的效果，这可能是因为之前的旧文件影响，
这时可以先清除编译输出再重新编译。

::

    #清除编译输出

    #Windows指令
    make.bat  clean
    #Ubuntu指令
    make clean

    #重新编译

    #Windows指令
    make.bat  html
    #Ubuntu指令
    make html
