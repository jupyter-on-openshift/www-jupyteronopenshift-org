Enabling JupyterLab Interface
-----------------------------

To enable the JupyterLab interface for a deployed notebook set the
``JUPYTER_ENABLE_LAB`` environment variable.

::

  oc set env dc/mynotebook JUPYTER_ENABLE_LAB=true

Setting the environment variable will trigger a new deployment and the
JupyterLab interface will be enabled.
