.. vim: syntax=rst


野火sphinx文档规范
==========================================

开源项目的整体目录：
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

.. highlight:: rst

注意：每次新添加了rst文档，必须要修改documentation文件夹下的index.rst文件，将新增的rst文件，添加到对应的地方。


图片
---------------------------------
文档引用的图片存储在文档源码目录下的media文件夹中，按部分、章节及文档分目录存储。

图片要直接使用如下形式,方便居中：

::

  .. image:: media/logo.png
     :align: center

不要使用如下形式，如下形式是docx转换后的格式，它不支持居中，见到要把它改好。
::

   |logo|

   .. |logo| image:: media/logo.png

rst格式检查
--------------------------
使用vscode的rst插件在编写时就会有格式检查。编写文档时应尽量满足该格式检查的规范。
对于docx转rst后的不规范文档，做到见一个改一个。

make html时，编译会有提示输出，尽量让它不输出的warning。


文档编码和回车
----------------
文档编码统一用“utf-8”， 回车使用“LF”，不要使用“CRLF”，文档编码和回车可在VS-Code的右下角设置。



代码引用
---------------------------------

超过3行的代码要加上行号、并用caption名指明代码片段的名，对于引用的代码文件，使用caption指明引用的路径名。

如以下语法：

::

   .. literalinclude:: ../../base_code/hello.c
      :caption: ../../base_code/hello.c
      :language: c
      :linenos:

类似docx的题注引用
------------------------
rst可通过链接实现类似doc的题注引用，它通过给内容添加 ``:name:`` 属性来实现，
代码、图片、表格等都可以使用这种方式，使用 ``:name:`` 属性来定义引用名，通过引用名+下划线来实现引用：



语法：
::

   .. literalinclude:: ../../base_code/hello.c
      :caption: ../../base_code/hello.c
      :language: c
      :name: 代码清单或自己起的引用名字
      :linenos:

   引用的方式是使用 ":name:"定义的名字加下划线 "_",如：

   代码清单或自己起的引用名字_

效果：

.. literalinclude:: ../../base_code/hello.c
   :caption: ../../base_code/hello.c
   :language: c
   :name: 代码清单或自己起的引用名字
   :linenos:

引用的方式是使用 ":name:"定义的名字加下划线 "_",如：

代码清单或自己起的引用名字_





语法：
::

   .. image:: ../media/rest-syntax/pic-video/logo.png
      :align: center
      :name: 野火logo

   引用的方式是使用 ":name:"定义的名字加下划线 "_",如：

   野火logo_

效果：

.. image:: ../media/rest-syntax/pic-video/logo.png
   :align: center
   :name: 野火logo

引用的方式是使用 ":name:"定义的名字加下划线 "_",如：

野火logo_


语法：

::

    .. list-table:: Frozen Delights!
        :widths: 15 10 30
        :header-rows: 1
        :name: 测试表格

        * - Treat
          - Quantity
          - Description
        * - Albatross
          - 2.99
          - On a stick!
        * - Crunchy Frog
          - 1.49
          - If we took the bones out, it wouldn't be
            crunchy, now would it?
        * - Gannet Ripple
          - 1.99
          - On a stick!

    引用的方式是使用 ":name:"定义的名字加下划线 "_",如：

    测试表格_


效果：

.. list-table:: Frozen Delights!
   :widths: 15 10 30
   :header-rows: 1

   * - Treat
     - Quantity
     - Description
   * - Albatross
     - 2.99
     - On a stick!
   * - Crunchy Frog
     - 1.49
     - If we took the bones out, it wouldn't be
       crunchy, now would it?
   * - Gannet Ripple
     - 1.99
     - On a stick!

引用的方式是使用 ":name:"定义的名字加下划线 "_",如：

    测试表格_

