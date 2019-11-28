.. vim: syntax=rst

.. highlight:: rst

超链接与文件引用
==========================================

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

    :ref:`about_embedfire <about_embedfire>`

    :ref:`about_embedfire`

效果：

:ref:`about_embedfire <about_embedfire>`

:ref:`about_embedfire`



引用非rst文档
^^^^^^^^^^^^^^^^^^^^^^^^

会呈现出点击后下载文件的效果。

语法：

::

    :download:`引用非rst的本地文档 <../requirements.txt>`.


效果：

:download:`引用非rst的本地文档 <../requirements.txt>`.

