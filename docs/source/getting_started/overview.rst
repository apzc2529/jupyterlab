.. Copyright (c) Jupyter Development Team.
.. Distributed under the terms of the Modified BSD License.

.. _overview:

快速上手
========

`JupyterLab <https://jupyterlab.readthedocs.io/en/latest/>`_ 是一款基于 Web的新一代 `Jupyter <https://docs.jupyter.org/en/latest/>`_ 用户界面。

.. image:: ../images/interface-jupyterlab.png
   :align: center
   :class: jp-screenshot
   :alt: JupyterLab 界面示例：文件浏览器、笔记本以及其他多个已打开的文件。

JupyterLab 让你能够以灵活、集成、并且可扩展的方式处理诸如 :ref:`Jupyter 笔记本 <notebook>`、文本编辑器、终端以及自定义组件等各类文档和活动。想要快速了解 JupyterLab 及其功能，你可以观看以下视频：

.. raw:: html

  <div class="jp-youtube-video">
    <iframe src="https://www.youtube-nocookie.com/embed/A5Yy..."0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  </div>

你可以在工作区中使用标签页和分割器 :ref:`打开并管理 <interface>` 所有文档和activities。文档与activities之间可以相互调用，从而启用交互式计算的新工作流，例如：

-  :ref:`code-console` 提供用于交互式运行代码的临时草稿本，并完整支持富输出。例如，代码控制台可以链接到某个笔记本内核，作为该笔记本的计算日志。
-  :ref:`Kernel 支持的文档 <kernel-backed-documents>` 使得任意文本文件（Markdown、Python、R、LaTeX 等）中的代码都可以在任意 Jupyter 内核中交互式运行。
-  笔记本的单元格输出可以被 :ref:`镜像到它们自己的标签页 <cell-output-mirror>`，与笔记本并排显示，由内核提供交互式控件支撑，从而轻松构建简单的仪表盘。
-  对同一文档使用不同编辑器或查看器进行多视图，使得对文档的实时编辑能反映到其他查看器中。例如，很容易对 :ref:`markdown`、:ref:`csv` 或 :ref:`vega-lite` 文档进行实时预览。

JupyterLab 还为查看与处理数据格式提供了统一模型。JupyterLab 能够识别并处理图像、CSV、JSON、Markdown、PDF、Vega、Vega‑Lite 等多种文件格式，并且能够以这些格式显示来自内核的富输出。更多信息请参见 :ref:`file-and-output-formats`。

为了更高效地在界面中导航，JupyterLab 提供了 :ref:`可自定义的键盘快捷键 <shortcuts>`。

通过 :ref:`扩展 <user_extensions>`，可以自定义或增强 JupyterLab 的任何部分，包括新主题、文件编辑器以及自定义组件。

JupyterLab 使用与经典 Jupyter Notebook 相同的 `notebook 文档格式 <https://nbformat.readthedocs.io/en/latest/>`__。

.. _classic:

经典 Notebook 将会怎样？
------------------------

随着 JupyterLab 4 的持续开发以及 Notebook 7 的跟进，Notebook 7 最终将取代经典的 Jupyter Notebook。
在这一过渡过程中，经典 Notebook、Notebook 7 与 JupyterLab 都会支持相同的 notebook 文档格式。
自 JupyterLab 4 起，Notebook Web 应用将不再与 JupyterLab 一同安装，因为它已不再是 JupyterLab 的依赖。
想了解生态中经典 Jupyter Notebook 的未来，请参阅
`Jupyter Notebook 7 文档 <https://jupyter-notebook.readthedocs.io/en/latest/migrate_to_notebook7.html>`__。


.. toctree::
   :maxdepth: 2

   installation
   starting
   issue
   faq
   changelog
   accessibility
   lifecycle
   ../privacy_policies
