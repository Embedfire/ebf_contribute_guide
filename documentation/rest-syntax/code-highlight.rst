.. vim: syntax=rst


代码高亮
=====================================

参考说明：
http://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html#toctree-directive

支持的高亮语言：
https://pygments.org/docs/lexers#lexers-for-various-shells


快速定义代码块
----------------------------------

使用简便的预定义高亮语法高亮缩进，默认不带语言说明的都使用highlight定义的语言高亮，
然后可以直接使用“::”两个冒号代替“code-block”指令快速定义其它代码块，
直到下一个highlight指令，才会改变语言：

.. highlight:: rst

::

   .. highlight:: sh

   此指令后如下的“::”定义的块都会以sh语法进行高亮，直到遇到下一条highlight指令。

   ::

      #此命令在主机执行
      sudo apt install python
      echo "helloworld,this is a script test!"

效果：

.. highlight:: sh


::

   #此命令在主机执行
   sudo apt install python
   echo "helloworld,this is a script test!"


code-block代码高亮
---------------------------------------

.. highlight:: rst

shell 高亮测试
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

高亮语法：


::

   .. code-block:: sh
      :caption: test
      :name: test333
      :emphasize-lines: 2
      :linenos:

      #此命令在主机执行
      sudo apt install python
      echo "helloworld,this is a script test!"

效果：

.. code-block:: sh
   :caption: sh test
   :name: test333
   :emphasize-lines: 2
   :linenos:

   #此命令在主机执行
   sudo apt install python
   echo "helloworld,this is a script test!"


C高亮测试
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

语法：


::

   .. code-block:: c
      :caption: c test
      :emphasize-lines: 4,5
      :linenos:

      #include <stdio.h>

      int main()
      {
         printf("hello, world! This is a C program.\n");
         for(int i=0;i<10;i++ ){
            printf("output i=%d\n",i);
         }

         return 0;
      }

效果：

.. code-block:: c
   :caption: c test
   :emphasize-lines: 4,5
   :linenos:

   #include <stdio.h>

   int main()
   {
      printf("hello, world! This is a C program.\n");
      for(int i=0;i<10;i++ ){
         printf("output i=%d\n",i);
      }

      return 0;
   }


verilog高亮测试
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


语法：

使用verilog或v进行高亮

::

   .. code-block:: v
      :caption: verilog test
      :emphasize-lines: 4,5
      :linenos:

      module  key_filter
      #(
         parameter CNT_MAX = 20'd999_999 //计数器计数最大值
      )
      (
         input   wire    sys_clk     ,   //系统时钟50Mhz
         input   wire    sys_rst_n   ,   //全局复位
         input   wire    key_in      ,   //按键输入信号

         output  reg     key_flag        //key_flag为1时表示消抖后检测到按键被按下
                                          //key_flag为0时表示没有检测到按键被按下
      );

效果：


.. code-block:: v
   :caption: verilog test
   :emphasize-lines: 4,5
   :linenos:

   module  key_filter
   #(
      parameter CNT_MAX = 20'd999_999 //计数器计数最大值
   )
   (
      input   wire    sys_clk     ,   //系统时钟50Mhz
      input   wire    sys_rst_n   ,   //全局复位
      input   wire    key_in      ,   //按键输入信号

      output  reg     key_flag        //key_flag为1时表示消抖后检测到按键被按下
                                       //key_flag为0时表示没有检测到按键被按下
   );


literalinclude直接嵌入本地文件并高亮
----------------------------------------------------------------------

嵌入整个文件
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

直接嵌入文件，包含标题、代码语言、高亮、带编号以及名称方便引用。

.. highlight:: rst



插入C代码
""""""""""""""""""""""""""""""""

::

   .. literalinclude:: ../../base_code/hello.c
      :caption: ../../base_code/hello.c
      :language: c
      :emphasize-lines: 5,7-12
      :linenos:
      :name: hello.c

效果：

.. literalinclude:: ../../base_code/hello.c
   :caption: ../../base_code/hello.c
   :language: c
   :emphasize-lines: 5,7-12
   :linenos:
   :name: hello.c



插入shell代码
""""""""""""""""""""""""""""""""

语法：

::

   .. literalinclude:: ../../base_code/hello_world.sh
      :caption: ../../base_code/hello_world.sh
      :language: sh
      :linenos:

效果：

.. literalinclude:: ../../base_code/hello_world.sh
   :caption: ../../base_code/hello_world.sh
   :language: sh
   :linenos:


插入Makefile代码
""""""""""""""""""""""""""""""""

语法：

::

   .. literalinclude:: ../../base_code/Makefile
      :caption: ../../base_code/Makefile
      :language: makefile
      :linenos:

效果：

.. literalinclude:: ../../base_code/Makefile
   :caption: ../../base_code/Makefile
   :language: makefile
   :linenos:

嵌入文件的某部分
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

通过lines指定嵌入文件的某些行。

语法：

::

   .. literalinclude:: ../../base_code/hello.c
      :caption: ../../base_code/hello.c
      :language: c
      :linenos:
      :lines: 1,3,5-8

效果：

.. literalinclude:: ../../base_code/hello.c
   :caption: ../../base_code/hello.c
   :language: c
   :linenos:
   :lines: 1,3,5-8





文件对比
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

语法：

::

   .. literalinclude:: ../../base_code/hello.c
   :diff: ../../base_code/hello_diff.c

效果：

.. literalinclude:: ../../base_code/hello.c
   :diff: ../../base_code/hello_diff.c


