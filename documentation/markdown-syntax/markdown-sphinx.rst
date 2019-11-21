.. vim: syntax=rst


.. highlight:: sh

使sphinx支持markdown
============================

sphinx默认是不支持markdown语法的，但可以通过插件来支持。

markdown基础支持
----------------------

recommonmark的PyPi说明：https://pypi.org/project/sphinx-markdown-tables/

recommonmark的sphinx说明：http://www.sphinx-doc.org/en/master/usage/markdown.html

recommonmark的使用说明：https://recommonmark.readthedocs.io/en/latest/index.html

::

   pip install recommonmark

在conf.py添加扩支持：
::

   extensions = ['recommonmark']

配置后就可以在sphinx中使用markdown文件了

markdown表格支持
---------------------------
要支持markdown的表格语法，还需要安装sphinx-markdown-tables

markdown表格支持：https://pypi.org/project/sphinx-markdown-tables/

安装：
::

   pip install sphinx-markdown-tables

使用：

在conf.py添加扩展支持：

::

   extensions = [
      'sphinx_markdown_tables',
   ]
