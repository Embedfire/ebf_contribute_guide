.. vim: syntax=rst

.. highlight:: rst

==========================================
ReST基础语法
==========================================

rst的基础语法和markdown差不多，

可以使用这个在线的rst编辑器了解相关语法：`rst在线编辑器 <http://rst.ninjs.org/>`_


- sphinx语法官网：http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html

- restruct语法官网：http://docutils.sourceforge.net/rst.html

下面是常用语法：


语法：

::

    一级标题
    ==============================

    二级标题
    ~~~~~~~~~~~~~~~

    三级标题
    ------------------

    四级标题
    ^^^^^^^^^^^^^^^^^^^^^

    五级标题
    """""""""""""""""

    六级标题
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


效果：


    一级标题
    ==============================

    二级标题
    ~~~~~~~~~~~~~~~

    三级标题
    ------------------

    四级标题
    ^^^^^^^^^^^^^^^^^^^^^

    五级标题
    """""""""""""""""

    六级标题
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


表格
-----------------------
表格语法说明：http://docutils.sourceforge.net/docs/ref/rst/directives.html#csv-table

推荐使用列表式表格，修改比较方便

列表式表格
^^^^^^^^^^^^

语法：

::

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

普通表格
^^^^^^^^^^^^^^^^

表格使用 == 号制作

语法示例：

::

    =====  =====  =======
    A      B      A and B
    =====  =====  =======
    False  False  False
    True   False  False
    False  True   False
    True   True   True
    =====  =====  =======

效果：

=====  =====  =======
A      B      A and B
=====  =====  =======
False  False  False
True   False  False
False  True   False
True   True   True
=====  =====  =======

在vscode可安装插件方便格式化表格：https://marketplace.visualstudio.com/items?itemName=shuworks.vscode-table-formatter

安装后通过Ctrl-Shift-P调用 Table: Format Current 或 Table: Format All


CSV表格
^^^^^^^^^^^^^^

使用CSV编写

::

    .. csv-table:: Frozen Delights!
        :header: "Treat", "Quantity", "Description"
        :widths: 15, 10, 30

        "Albatross", 2.99, "On a stick!"
        "Crunchy Frog", 1.49, "If we took the bones out, it wouldn't be
        crunchy, now would it?"
        "Gannet Ripple", 1.99, "On a stick!"

效果：

.. csv-table:: Frozen Delights!
   :header: "Treat", "Quantity", "Description"
   :widths: 15, 10, 30

   "Albatross", 2.99, "On a stick!"
   "Crunchy Frog", 1.49, "If we took the bones out, it wouldn't be
   crunchy, now would it?"
   "Gannet Ripple", 1.99, "On a stick!"
