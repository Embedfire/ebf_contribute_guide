.. vim: syntax=rst


图片与视频
==========================================


图片
----------------------
图片原文件统一存储在引用文档所在的同级目录的 **media** 文件夹下。

显示图片直接使用image指令，无特殊情况的话我们书籍图片要求使用居中方式显示：

.. image:: ../media/rest-syntax/pic-video/logo.png
   :align: center


以下的图片显示方式是word自动转换的结果，使用这种方式无法以居中形式显示图片，所以我们要修改。

它的原理是使用“||”类似宏的方式替换指令，使rst源码看起来更简洁，但不能居中显示。


|logo|

.. |logo| image:: ../media/rest-syntax/pic-video/logo.png

图片还可以使用 width、heigh、scale等参数，但不推荐使用，设置过width、height参数的图片，
在页面可以点击查看原图。

.. image:: ../media/rest-syntax/pic-video/logo.png
   :align: center
   :width: 5.63529in
   :height: 0.97222in
