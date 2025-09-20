.. Copyright (c) Jupyter Development Team.
.. Distributed under the terms of the Modified BSD License.

.. _installation:

安装
====

JupyterLab 可以作为**终端启动的应用**（在命令行中运行 ``jupyter lab``）进行安装，也可以作为**桌面应用**安装与使用；后者的安装说明详见 JupyterLab Desktop 仓库中的 `Installation 文件<https://github.com/jupyterlab/jupyterlab-desktop#installation>`__。

.. warning::
    新版本的 JupyterLab 可能会与现有扩展或其它 Jupyter 自定义代码产生**向后兼容性破坏**。正如 :ref:`versioning_notes` 所述，JupyterLab 的开发与发布遵循语义化版本（SemVer）。因此，建议在打算安装或升级JupyterLab时，需提前评估可能由此代理的破坏性变更，以免影响 JupyterLab 及相关工具的正常使用。

conda
-----

如果使用 ``conda``，可以通过以下命令安装：

.. code:: bash

    conda install -c conda-forge jupyterlab

mamba
-----

如果使用 ``mamba``，可以通过以下命令安装：

.. code:: bash

    mamba install -c conda-forge jupyterlab

pip
---

如果使用 ``pip``，可以通过以下命令安装：

.. code:: bash

    pip install jupyterlab

若使用 ``pip install --user`` 在当前用户目录进行安装，需要将 ``$HOME/.local/bin`` 目录添加到环境变量 ``PATH`` 中，然后才能在终端中启动 ``jupyter lab``。在类 Unix 系统（FreeBSD、GNU/Linux、macOS）中，可以执行：``export PATH="$HOME/.local/bin:$PATH"``。

pipenv
------

如果使用 ``pipenv``，可以这样安装：

.. code:: bash

    pipenv install jupyterlab
    pipenv shell

在使用 ``pipenv`` 的项目中，启动 ``jupyter lab`` 前需**激活项目虚拟环境**。例如，在 ``pipenv`` 的 ``Pipfile`` 与 ``Pipfile.lock`` 所在目录（即运行上述命令的目录）中：

.. code:: bash

    pipenv shell
    jupyter lab

或者，也可以直接在虚拟环境中直接运行：

.. code:: bash

    pipenv run jupyter lab

Docker
------

如果你已安装 `Docker <https://docs.docker.com/install/>`__，可以从 Jupyter 团队维护的众多 `Docker 镜像 <https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html>`__ 中选择选择合适的版本并安装、使用 JupyterLab。请参照 `Jupyter Docker Stacks 指南 <https://jupyter-docker-stacks.readthedocs.io/en/latest/>`__ 选择并部署镜像。

请确保在启动容器时为 ``docker`` 命令添加 ``-e JUPYTER_ENABLE_LAB=yes`` 标志，以启用容器中的 JupyterLab。

使用 JupyterHub
---------------------

详见文档页面：:ref:`JupyterHub 环境中的 JupyterLab <jupyterhub>`。

使用 Jupyverse
--------------------

`Jupyverse <https://github.com/jupyter-server/jupyverse/>`__ 是一个基于 `FastAPI <https://fastapi.tiangolo.com/>`__ 的下一代 Jupyter 服务器。它可作为
`jupyter-server <https://github.com/jupyter-server/jupyter_server/>`__（JupyterLab 默认安装的服务器）的替代方案。需要注意的是，``jupyter-server`` 的扩展在 ``jupyverse`` 中不可用（但可能存在功能等价的插件）。

可以使用 ``pip`` 安装 ``jupyverse``：

.. code:: bash

    pip install "jupyverse[auth,jupyterlab]"

或使用 ``conda``：

.. code:: bash

    conda install -c conda-forge jupyverse fps-auth fps-jupyterlab

或使用 ``mamba``：

.. code:: bash

    mamba install -c conda-forge jupyverse fps-auth fps-jupyterlab

安装完成后，可通过以下命令启动：

.. code:: bash

    jupyverse

支持的浏览器
------------------

以下浏览器的**最新版本**已知可正常工作：

-  Firefox
-  Chrome
-  Safari
-  Edge

更早的浏览器版本可能也能运行，但**不作保证**。

安装问题排查
---------------------

如果你的电脑所在网络出口使用了**代理或防火墙**，可能会因为代理或防火墙规则导致 HTTP/SSL 错误。例如，当 ``conda`` 无法连接其软件仓库时，你可能会看到类似错误::

    CondaHTTPError: HTTP 000 CONNECTION FAILED for url <https://repo.anaconda.com/pkgs/main/win-64/current_repodata.json>

以下是一些常见的第三方站点，它们托管了 Python/Conda/npm 等生态中的软件包。你的 IT 部门可能需要对这些域名放行 http / https 访问：

- pypi.org
- pythonhosted.org
- continuum.io
- anaconda.com
- conda.io
- github.com
- githubusercontent.com
- npmjs.com
- yarnpkg.com

或者，你也可以为代理配置一个**有权限的域用户（含密码）**，以便能够正常联网。最常见的做法是设置两类环境变量：``HTTP_PROXY`` 与 ``HTTPS_PROXY``。正确配置这些变量后，就可以使用 ``conda`` 等在内的众多开源工具。

.. code:: bash

    # Windows
    set HTTP_PROXY=http://USER:PWD@proxy.company.com:PORT
    set HTTPS_PROXY=https://USER:PWD@proxy.company.com:PORT

    # Linux / macOS
    export HTTP_PROXY=http://USER:PWD@proxy.company.com:PORT
    export HTTPS_PROXY=https://USER:PWD@proxy.company.com:PORT

你还可以通过如下命令，为 npm 设置代理或更换仓库（registry）：

.. code:: bash

    # 为 NPM 设置代理
    npm config set proxy http://USER:PWD@proxy.company.com:PORT
    npm config set proxy https://USER:PWD@proxy.company.com:PORT

    # 设置默认的 NPM 仓库（可选；当常用 JS 库无法找到时有用）
    npm config set registry http://registry.npmjs.org/
    jlpm config set npmRegistryServer https://registry.yarnpkg.com/

当能用 HTTP 上网，而不能使用HTTPS时，可能会导致 ``npm`` 安装失败。此时可以配置``npm`` 禁用 SSL：

.. warning::  **不建议**禁用 SSL，这很有可能会产生安全隐患。请仅在确实必要且明确知情相关风险时，设置禁用SSL。

.. code:: bash

    # 让 npm 不使用 SSL
    npm set strict-ssl False
