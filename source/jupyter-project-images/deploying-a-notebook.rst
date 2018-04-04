Deploying a Notebook
--------------------

To deploy a notebook from the command line using the template, run::

    oc new-app --template jupyter-notebook

The output will be similar to::

    --> Deploying template "jupyter/jupyter-notebook" to project jupyter

         Jupyter Notebook
         ---------
         Template for deploying Jupyter Notebook images.

         * With parameters:
            * APPLICATION_NAME=notebook
            * NOTEBOOK_IMAGE=jupyter/minimal-notebook:latest
            * NOTEBOOK_PASSWORD=ded4d7cada554aa48e0db612e1ed1080 # generated

    --> Creating resources ...
        configmap "notebook-cfg" created
        deploymentconfig "notebook" created
        route "notebook" created
        service "notebook" created
    --> Success
        Access your application via route 'notebook-jupyter.abcd.pro-us-east-1.openshiftapps.com'
        Run 'oc status' to view your app.

When no template parameters are provided, the name of the deployed notebook
will be ``notebook``. The image used will be::

    jupyter/minimal-notebook:latest

A password you can use when accessing the notebook will be auto generated
and is displayed in the output from running ``oc new-app``.

To see the hostname for accessing the notebook run::

    oc get routes

The output will be similar to::

    NAME      HOST/PORT                                              PATH  SERVICES  PORT      TERMINATION    WILDCARD
    notebook  notebook-jupyter.abcd.pro-us-east-1.openshiftapps.com        notebook  8888-tcp  edge/Redirect  None

A secure route will be used to expose the notebook outside of the OpenShift
cluster, so in this case the URL would be::

    https://notebook-jupyter.abcd.pro-us-east-1.openshiftapps.com/

When prompted, enter the password for the notebook.
