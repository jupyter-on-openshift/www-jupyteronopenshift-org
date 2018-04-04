Enabling Jupyter Lab Interface
------------------------------

To enable the Jupyter Lab interface for a deployed notebook set the
``JUPYTER_ENABLE_LAB`` environment variable.

::

  oc set env dc/mynotebook JUPYTER_ENABLE_LAB=true

Setting the environment variable will trigger a new deployment and the
Jupyter Lab interface will be enabled.
