.. vim: syntax=rst


代码高亮
=====================================

参考说明：
http://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html#toctree-directive

支持的高亮语言：
https://pygments.org/docs/lexers#lexers-for-various-shells

直接嵌入文件，包含标题、代码语言、高亮、带编号以及名称方便引用

.. literalinclude:: ../../base_code/hello.c
   :caption: ../../base_code/hello.c
   :language: c
   :emphasize-lines: 5,7-12
   :linenos:
   :name: hello.c



嵌入文件的某些行：

.. literalinclude:: ../../base_code/hello.c
   :caption: ../../base_code/hello.c
   :language: c
   :linenos:
   :lines: 1,3,5-8

shell代码：

.. literalinclude:: ../../base_code/hello_world.sh
   :caption: ../../base_code/hello_world.sh
   :language: sh
   :linenos:


Makefile:

.. literalinclude:: ../../base_code/Makefile
   :caption: ../../base_code/Makefile
   :language: makefile
   :linenos:

文件对比：

.. literalinclude:: ../../base_code/hello.c
   :diff: ../../base_code/hello_diff.c


shell 高亮测试：

.. code-block:: sh
   :caption: test
   :name: test333
   :linenos:

   #此命令在主机执行
   sudo apt install python
   echo "helloworld,this is a script test!"

.. code-block:: sh
   :name: test2

   #此命令在主机执行
   sudo apt install python
   echo "helloworld,this is a script test!"

使用简便的预定义高亮语法高亮缩进，默认不带语言说明的都使用highlight定义的语言：

.. highlight:: sh

直到下一个highlight指令，才会改变语言

::

   #此命令在主机执行
   sudo apt install python
   echo "helloworld,this is a script test!"

python 高亮测试：

.. code-block:: python
   :name: test555

   def some_function():
       interesting = False
       print 'This line is highlighted.'
       print 'This one is not...'
       print '...but this one is.'


图片
----------------------
图片原文件统一存储在引用文档所在的同级目录的 **media** 文件夹下。

显示图片直接使用image指令，无特殊情况的话我们书籍图片要求使用居中方式显示：

.. image:: media/logo.png
   :align: center


以下的图片显示方式是word自动转换的结果，使用这种方式无法以居中形式显示图片，所以我们要修改。

它的原理是使用“||”类似宏的方式替换指令，使rst源码看起来更简洁，但不能居中显示。


|logo|

.. |logo| image:: media/logo.png

图片还可以使用 width、heigh、scale等参数，但不推荐使用，设置过width、height参数的图片，
在页面可以点击查看原图。

.. image:: media/logo.png
   :align: center
   :width: 5.63529in
   :height: 0.97222in
