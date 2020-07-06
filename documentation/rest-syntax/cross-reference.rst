.. vim: syntax=rst

.. highlight:: rst

超链接与文件引用
==========================================

参考说明：http://www.sphinx-doc.org/en/master/usage/restructuredtext/roles.html#ref-role

超链接
---------------
语法：

::

    直接嵌入网址：
    `野火公司官网 <http://www.embedfire.com>`_

    使用引用的方式把具体网址定义在其它地方： `野火公司官网`_

    .. _野火公司官网: http://www.embedfire.com

效果：



直接嵌入网址：

`野火公司官网 <http://www.embedfire.com>`_

使用引用的方式把具体网址定义在其它地方： `野火公司官网`_

.. _野火公司官网: http://www.embedfire.com




引用
--------------------------

引用图片、表格
^^^^^^^^^^^^^^^^^^^^^^^

在图片、表格上面加一个引用标签，然后通过 ref指令引用。
语法：

::

    .. _my-reference-label支持中文:

    .. figure: ../media/rest-syntax/pic-video/logo.png
       :alt: 野火logo
       :align: center

    引用方式 :ref:`my-reference-label支持中文` 。


效果：

.. _my-reference-label支持中文:

.. figure:: ../media/rest-syntax/pic-video/logo.png
    :alt: 野火logo
    :align: center

    必须写这个图片名

引用方式 :ref:`my-reference-label支持中文` 。

表格引用：

::

    .. _拨码开关启动配置表:

    .. table:: 拨码开关启动配置表

    ==== ====== ========== ==== == ===
    编号 名称   NAND FLASH eMMC SD USB
    ==== ====== ========== ==== == ===
    1    MODE0  0          0    0  1
    2    MODE1  1          1    1  0
    3    CFG1-4 1          0    0  X
    4    CFG1-5 0          1    0  X
    5    CFG1-6 0          1    1  X
    6    CFG1-7 1          0    0  X
    7    CFG2-3 0          1    0  X
    8    CFG2-5 0          0    1  X
    ==== ====== ========== ==== == ===

    引用示例 :ref:`拨码开关启动配置表` 。
    自定义名称引用 :ref:`自定义名称 <拨码开关启动配置表>` 。

效果：

.. _拨码开关启动配置表:

.. table:: 拨码开关启动配置表

    ==== ====== ========== ==== == ===
    编号 名称   NAND FLASH eMMC SD USB
    ==== ====== ========== ==== == ===
    1    MODE0  0          0    0  1
    2    MODE1  1          1    1  0
    3    CFG1-4 1          0    0  X
    4    CFG1-5 0          1    0  X
    5    CFG1-6 0          1    1  X
    6    CFG1-7 1          0    0  X
    7    CFG2-3 0          1    0  X
    8    CFG2-5 0          0    1  X
    ==== ====== ========== ==== == ===

引用示例 :ref:`拨码开关启动配置表` 。
自定义名称引用 :ref:`自定义名称 <拨码开关启动配置表>` 。

引用文档
^^^^^^^^^^^^^^^^^^^^^^^

语法：

::

    自定义引用文字

    :doc:`引用本地的其它rst文档,rst后缀要省略，如about_us <../about_us>`

    使用标题文字
    :doc:`../about_us`

效果：

自定义引用文字

:doc:`引用本地的其它rst文档,rst后缀要省略，如about_us <../about_us>`

使用标题文字
:doc:`../about_us`


使用标签引用文档
^^^^^^^^^^^^^^^^^^^^^^^



要在被引用的文件头定义标签，如about_us.rst文件头写 “about_embedfire” 的标签，具体请查看该文档的源码


语法：
::

    :ref:`自定义链接文字 <about_embedfire>`

    :ref:`about_embedfire`

效果：

:ref:`about_embedfire <about_embedfire>`

:ref:`about_embedfire`

若要跨文档引用标题，可以使用自动切片扩展插件，它的使用方式如下：

某个文档：

::

    =============
    Some Document
    =============


    Internal Headline
    =================

然后在另一个文档引用：

::

    ===============
    Some Other Doc
    ===============


    A link-  :ref:`Internal Headline`


此扩展程序是内置的，因此您只需编辑即可 conf.py

::

    extensions = [
        .
        . other
        . extensions
        . already
        . listed
        .
        'sphinx.ext.autosectionlabel',
    ]

您唯一需要注意的是，现在您无法在整个文档集合中复制内部标题。

引用非rst文档
^^^^^^^^^^^^^^^^^^^^^^^^

会呈现出点击后下载文件的效果。注意这种引用方式在生成pdf文件时链接会无效。

语法：

::

    :download:`引用非rst的本地文档 <../requirements.txt>`.


效果：

:download:`引用非rst的本地文档 <../requirements.txt>`.

