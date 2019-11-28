.. vim: syntax=rst


特殊提示
==========================================
特殊提示支持警告、重要、提示、注意等标签，适合做显眼的用途。

- attention
- caution
- danger
- error
- hint
- important
- note
- tip
- warning

.. highlight:: rst

语法：

::

  .. note:: This is a note admonition.
   This is the second line of the first paragraph.

   - The note contains all indented body elements
     following.
   - It includes this bullet list.

  .. hint:: This is a hint admonition.

  .. important:: This is a important admonition.

  .. tip:: This is a tip admonition.

  .. warning:: This is a warning admonition.

  .. caution:: This is a caution admonition.

  .. attention:: This is a attention admonition.

  .. error:: This is a error admonition.

  .. danger:: This is a danger admonition.



效果：

.. note:: This is a note admonition.
   This is the second line of the first paragraph.

   - The note contains all indented body elements
     following.
   - It includes this bullet list.

.. hint:: This is a hint admonition.

.. important:: This is a important admonition.

.. tip:: This is a tip admonition.

.. warning:: This is a warning admonition.

.. caution:: This is a caution admonition.

.. attention:: This is a attention admonition.

.. error:: This is a error admonition.

.. danger:: This is a danger admonition.

