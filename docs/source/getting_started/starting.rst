.. Copyright (c) Jupyter Development Team.
.. Distributed under the terms of the Modified BSD License.

.. _starting:

启动 JupyterLab
=====================================

在终端中运行：

.. code:: bash

    jupyter lab

JupyterLab 会自动在浏览器中打开。

如果 Notebook 文件不在当前目录，可以在启动时指定工作目录路径。
**建议不要在根目录运行**（如 Windows 的 ``C:\`` 或 Linux 的 ``/``），以免误修改系统文件。

示例：

.. code:: bash

    # Windows 示例
    jupyter lab --notebook-dir=E:/ --preferred-dir E:/Documents/Somewhere/Else
    # Linux 示例
    jupyter lab --notebook-dir=/var/ --preferred-dir /var/www/html/example-app/

你也可以在浏览器中输入 Notebook 服务器的 :ref:`URL <urls>` 来访问 JupyterLab。
每个 JupyterLab 会话都位于一个 :ref:`工作区 <workspaces>`，默认工作区对应 ``/lab`` URL：

.. code-block:: none

  http(s)://<server:port>/<lab-location>/lab

与经典 Notebook 一样，JupyterLab 支持复制 URL 来 :ref:`直接打开指定的 Notebook 或文件 <url-tree>`。
此外，URL 机制还是 JupyterLab 界面的高级功能，可以用来管理 :ref:`工作区 <url-workspaces>`。更多信息见 :ref:`urls`。

JupyterLab 基于 Jupyter Server 运行。安全相关内容请参考 Jupyter Server 文档的
`security section <https://jupyter-server.readthedocs.io/en/latest/operators/security.html>`__。
