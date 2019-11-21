.. vim: syntax=rst



基础语法
==============

rst的基础语法和markdown差不多，

可以使用这个在线的rst编辑器了解相关语法：`rst在线编辑器 <http://rst.ninjs.org/>`_

下面是常用格式，请直接查看源码及使用vscode预览查看




一级标题
==============================

二级标题
------------------

三级标题
^^^^^^^^^^^^^^^^^^^^^

四级标题
"""""""""""""""""

五级标题
*****************

**强调**

*斜体*

``monospace,会变色，具体作用不清楚``

无序列表
---------------------------
- hhhhhhhh
- hhhhhhhh
- hhhhhhhh
- hhhhhhhh
- hhhhhhhh
- hhhhhhhh

有序列表
------------------------
支持数字、大小写字母和罗马数字

1. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh

a. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh
#. hhhhhhhh

超链接
---------------
`野火公司官网 <http://www.embedfire.com>`_


引用
--------------------------

引用文档
^^^^^^^^^^^^^^^^^^^^^^^

自定义引用文字

:doc:`引用本地的其它rst文档,rst后缀要省略，如about_us <../about_us>`

使用标题文字
:doc:`../about_us`


使用标签引用文档
^^^^^^^^^^^^^^^^^^^^^^^

要在被引用的文件头定义标签，如about_us.rst文件头写 “about_embedfire” 的标签，具体请查看该文档的源码

:ref:`about_embedfire <about_embedfire>`

:ref:`about_embedfire`

引用非rst文档
^^^^^^^^^^^^^^^^^^^^^^^^

:download:`引用非rst的本地文档 <../requirements.txt>`.


代码高亮
^^^^^^^^^^^^^^^^^^^^^^^^^

参考说明：
http://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html#toctree-directive

支持的高亮语言：
https://pygments.org/docs/lexers#lexers-for-various-shells

直接嵌入文件，包含标题、代码语言、高亮、带编号以及名称方便引用

.. literalinclude:: ../../base_code/hello.c
   :caption: ../../base_code/hello.c
   :language: c
   :emphasize-lines: 12,15-18
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
   :lines: 1,3,5-8

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
   :name: install
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
   :name: install

   def some_function():
       interesting = False
       print 'This line is highlighted.'
       print 'This one is not...'
       print '...but this one is.'

