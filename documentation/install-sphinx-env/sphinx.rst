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
^^^^^^^^^^^^^^^^

windows直接到python官网下载安装

Ubuntu下使用如下指令安装：
::

    sudo apt install python3

安装sphinx
^^^^^^^^^^^^^^^^^^
windows下使用如下指令安装：

::

    py -3 -m pip install sphinx
    #国内用户推荐使用清华源安装，使用-i指定源
    py -3 -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx

Ubuntu下使用如下指令安装

::

    python3 -m pip install sphinx
    #国内用户推荐使用清华源安装，使用-i指定源
    python3 -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx
    
    #Ubuntu下可能还需要安装如下软件包
    apt-get install python3-sphinx




使用模板创建sphinx文档
----------------------

本项目的sphinx已适配好支持markdown、默认的readthedoc主题等内容。

如果是要编写新的书籍，推荐直接使用本项目文档作为模版，修改conf.py文件的配置即可改变项目的名字、主题之类的内容。

下载项目源码
^^^^^^^^^^^^^^^^^^^

先从github下载本项目源代码：

::

    git clone git@github.com:Embdefire/ebf_contribute_guide.git

下载完成后，可看到本项目的结构大致如下：

::

  ├── README                    说明文档或软链接至documentation中的说明，方便github阅读
  ├── base_code                 配套代码
  └── documentation             配套文档
      ├── faq                   存储常见问题的文档
      ├── about_us.rst          关于我们
      ├── _build                文档编译输出目录
      ├── conf.py               sphinx配置文件
      ├── contribute            如何参与项目，贡献与投稿的说明
      ├── foreword.rst          前言
      ├── index.rst             目录
      ├── make.bat
      ├── Makefile
      ├── media                 文档中使用的图片文件
      ├── requirements.txt      文档的python依赖
      ├── _static
      ├── _templates
      ├── TODO.rst              待完成的内容，发布的任务列表

特别内容说明如下：

- **base_code** ：该目录通常存放项目的代码，
- **documentation** ：该目录通常存放项目的文档内容，如我们的rst、markdown文档。

安装python依赖包
^^^^^^^^^^^^^^^^^^^

使用时，要先根据项目的 **documentation/requirements.txt** 安装依赖的python包。

::

    #切换至requirements.txt文件的同级目录
    cd documentation

    #requirements.txt文件的同级目录下执行后面的命令

    #Windows指令，推荐使用powershell运行
    py -3 -m pip install -r requirements.txt
    #Ubuntu指令
    python3 -m pip install -r  requirements.txt

    #国内用户推荐使用清华源安装
    #Windows指令，推荐使用powershell运行
    py -3 -m pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
    #Ubuntu指令
    python3 -m pip install -r  requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple


编写文档
^^^^^^^^^^^^^^^^^^^^
安装好后，在项目的文档目录中添加rst或markdown文件即可，
建议使用vs code来编写文档，它非常方便预览文档，
可参考《 :doc:`vscode`》来搭建vscode预览sphinx文档的环境。

编写文档时的语法和规范可参考以下内容：

- 《 :doc:`../rest-syntax/base-syntax`》
- 《 :doc:`../rest-syntax/rule`》
- 《 :doc:`../markdown-syntax/markdown-demo`》



编译文档
-------------------------
如果使用了vscode的rst插件，可以直接保存rst文件后它会自动编译并可预览。

也可以手动编译，到文档源码所在的makefile目录，执行如下命令：

::

    #在文档的makefile目录下执行

    #Windows指令
    make.bat  html
    #Ubuntu指令
    make html

在设定的build或_build的html目录下会生成静态的html文件。可直接使用这些静态的html文件制作网站。




在本地预览文档
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

允许其它主机预览文档
------------------------------
类似地，若要允许其它主机访问自己的文档，执行如下命令即可

::

    #在生成的html目录执行如下指令
    #Windows
    py -3 -m http.server --bind 0.0.0.0 8000

    #Ubuntu
    python3 -m http.server --bind 0.0.0.0 8000

运行指令后，在浏览器中打开 http://主机IP:8000 即可查看生成的静态网页。


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



创建全新的sphinx文档
----------------------
若不想使用本工程模版，可以使用如下指令创建全新的文档。

::

    sphinx-quickstart

按照提示回答问题即可。
推荐使用默认的_build目录，与vscode保持一致。
其中提示语言时可以使用这个中文代码：zh_CN

sphinx默认不支持markdown语法，要支持的话请参考本模版的conf.py文件配置。
