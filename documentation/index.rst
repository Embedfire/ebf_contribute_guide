.. [野火]sphinx文档规范与模版 documentation master file, created by
   sphinx-quickstart on Thu Nov 21 10:50:33 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. 这一页是目录树

[野火]sphinx文档规范与模版
======================================================

.. toctree::
   :maxdepth: 1
   :caption: 为什么使用sphinx写文档

   about_us
   TODO
   foreword
   contribute/rule

.. toctree::
   :maxdepth: 2
   :caption: 使用sphinx和vscode编写文档
   :titlesonly:
   :numbered:

   install-sphinx-env/sphinx
   install-sphinx-env/vscode

.. glob可以自动搜索符合的目标，但不适合顺序编号
.. 对顺序无要求的目录可以使用这种方式
.. .. toctree::
..    :maxdepth: 1
..    :caption: 安装sphinx开发环境
..    :titlesonly:
..    :numbered:
..    :glob:
..    install-sphinx-env/*

.. 二级目录表示法
.. .. toctree::
..    :maxdepth: 2
..    :caption: reST语法
..    :titlesonly:
..
..    rest-syntax/index



.. 这是二级目录树的使用范例

.. toctree::
   :maxdepth: 2
   :caption: reST语法
   :titlesonly:

   rest-syntax/base-syntax
   rest-syntax/cross-reference
   rest-syntax/code-highlight
   rest-syntax/pic-video
   rest-syntax/admonition
   rest-syntax/directive-role

.. toctree::
   :maxdepth: 1
   :caption: 使用markdown

   markdown-syntax/markdown-sphinx

.. toctree::
   :maxdepth: 1
   :caption: 文档格式转换

   format-convert/pandoc

.. toctree::
   :maxdepth: 1
   :caption: 发布文档到readthedoc
