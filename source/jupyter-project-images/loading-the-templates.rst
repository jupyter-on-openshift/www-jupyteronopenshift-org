Loading the Templates
---------------------

The templates for OpenShift are kept in an examples directory of the
``docker-stacks`` repository of the Jupyter Project.

To load the templates, login to your OpenShift cluster from the command
line using ``oc``, ensure you are in the correct project, and then run::

    oc create -f https://raw.githubusercontent.com/jupyter-on-openshift/docker-stacks/master/examples/openshift/templates.json

This should create the following templates::

    jupyter-notebook

The template can be used from the command line using the ``oc new-app``
command, or from the OpenShift web console by selecting *Add to Project*
and then *Select from Project*.
