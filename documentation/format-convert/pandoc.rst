.. vim: syntax=rst

.. highlight:: sh

使用pandoc进行文档转换
============================

使用pandoc可以方便地对文档的格式进行相互转换。

安装
-----------------------

pandoc安装说明：https://github.com/jgm/pandoc/blob/master/INSTALL.md

pandoc用户手册：https://pandoc.org/MANUAL.html

根据系统按它的说明下载对应的安装包即可，ubuntu下不要直接用apt安装，apt安装的版本太旧。

在ubuntu下可以使用如下命令查看pandoc的说明：

::

    man pandoc


docx转rst
----------------------------

使用python安装rstdoc扩展包，方便转换：https://pypi.org/project/rstdoc/


docx转rst操作步骤：

- 先把docx文档按章节分开，一个章节一个docx文档，不然整个文档转换可能太大，
  导致错误，而且整个文档转换图片或内容不方便处理。

- 使用rstfromdocx命令一个个文档转换成rst

使用如下指令转换
::

    #doc1为要转换的文档
    rstfromdocx -lurg doc1.docx

命令执行后会生成与文档名相同的目录，目录下是sphinx形式的rest文档，
把rest文档复制至新的书籍目录并把后缀改为rst，media下的图片也放到目标书籍的同级目录即可。

.. tip:: 在Windows转换后，生成的文件目录引用使用的路径是“\”，而sphinx路径只支持“/”，
   所以图片之类的引用路径要注意修改。


pandoc  rst转docx
------------------------------------
rstdocx插件据说可以更完美地把rst转成docx，但还不清楚rstdocx插件如何把rst转成docx，但用pandoc可满足基本要求。

::

    pandoc rstfile.rst  -f   rst  -t docx  -o targetdocfile.docx  --data-dir=sourcedir  --reference-doc=module.docx

- 其中rstfile.rst是源文件，-f 指源格式，-f 指目标格式
- -o指定的是输出文件
- --data-dir=指定的是依赖目录
- --reference-doc=是docx模版文件，使用模版文件转换可以把标题之类的格式搞得更规范

reference-doc模版及说明：https://pandoc.org/MANUAL.html#option--reference-doc

pandoc docx转rst
-------------------------------
与rst转docx类似，输出的图片目录可以使用这个参数设置：

--extract-media=DIR
