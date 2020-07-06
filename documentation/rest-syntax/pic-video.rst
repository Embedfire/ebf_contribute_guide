.. vim: syntax=rst


图片与视频
==========================================

添加图片的sphinx说明：http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html
添加图片的rst官方说明：


图片
----------------------
图片原文件统一存储在引用文档所在的同级目录的 **media** 文件夹下。

显示图片直接使用image或figure指令，无特殊情况的话我们书籍图片要求使用居中方式显示，
还需要添加“alt”选项指定图片的描述（类似doc中的题注），以便图片加载失败时显示文字

**不要使用bmp图片** ，bmp图片在生成pdf的时候会丢失，所以不要使用bmp格式的图片。

figure命令
~~~~~~~~~~~~~~~

语法：

::

    .. figure: ../media/rest-syntax/pic-video/logo.png
       :alt: 野火logo
       :align: center
       :caption: 野火logo


效果：

.. figure:: ../media/rest-syntax/pic-video/logo.png
    :alt: 野火logo
    :align: center


image命令：
~~~~~~~~~~~~~~~

语法：
::

    .. image:: ../media/rest-syntax/pic-video/logo.png
       :align: center
       :alt: 野火logo

效果：

.. image:: ../media/rest-syntax/pic-video/logo.png
   :align: center
   :alt: 野火logo





以下的图片显示方式是word自动转换的结果，使用这种方式无法以居中形式显示图片，所以我们要修改。

它的原理是使用“||”类似宏的方式替换指令，使rst源码看起来更简洁，但不能居中显示。

语法：

::

    |logo|,使用"|宏名|"的形式替换文字。

    .. |logo| image:: ../media/rest-syntax/pic-video/logo.png



效果：

|logo|,使用"|"宏名"|"的形式替换文字。

.. |logo| image:: ../media/rest-syntax/pic-video/logo.png

图片还可以使用 width、heigh、scale等参数，但不推荐使用，设置过width、height参数的图片，
在页面可以点击查看原图。

语法：
::

    .. image:: ../media/rest-syntax/pic-video/logo.png
       :align: center
       :width: 5.63529in
       :height: 0.97222in

效果：

.. image:: ../media/rest-syntax/pic-video/logo.png
   :align: center
   :width: 5.63529in
   :height: 0.97222in

视频
-----------------------------


使用raw指令插入html代码。
直接粘贴视频网站的通用html代码，不过貌似不能放大。

在vscode可能无法预览，直接在浏览器中看即可。

.. note::

    TODO：目前还不知道如何放大，以及点击后到具体的视频网站播放。

哔哩哔哩
^^^^^^^^^^^^^^^^^^^^

语法：
::

    .. raw:: html

    <iframe src="//player.bilibili.com/player.html?aid=70961112&cid=122951107&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

效果：

.. raw:: html

    <iframe src="//player.bilibili.com/player.html?aid=70961112&cid=122951107&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>


优酷
^^^^^^^^^^^^^^^^^^^^^^^^^^^
语法：
::

    .. raw:: html

    <iframe height=498 width=510 src='http://player.youku.com/embed/XMzk2MzQxNTQ3Ng==' frameborder=0 'allowfullscreen'></iframe>

