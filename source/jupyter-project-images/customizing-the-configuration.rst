Customizing the Configuration
-----------------------------

If you want to set any custom configuration for the notebook, you can edit
the config map created by the template.

::

    oc edit configmap/mynotebook-cfg

The ``data`` field of the config map contains Python code used as the
``jupyter_notebook_config.py`` file.

If you are using a persistent volume, you can also create a configuration
file at::

    /home/jovyan/.jupyter/jupyter_notebook_config.py

This will be merged at the end of the configuration from the config map.

Because the configuration is Python code, ensure any indenting is correct.
Any errors in the configuration file will cause the notebook to fail when
starting.

If the error is in the config map, edit it again to fix it and trigger a
new deployment if necessary by running::

    oc rollout latest dc/mynotebook

If you make an error in the configuration file stored in the persistent
volume, you will need to scale down the notebook so it isn't running.

::

    oc scale dc/mynotebook --replicas 0

Then run::

    oc debug dc/mynotebook

to run the notebook in debug mode. This will provide you with an
interactive terminal session inside a running container, but the notebook
will not have been started. Edit the configuration file in the volume to
fix any errors and exit the terminal session.

Start up the notebook again.

::

    oc scale dc/mynotebook --replicas 1
