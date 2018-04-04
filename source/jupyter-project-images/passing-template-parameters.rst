Passing Template Parameters
---------------------------

To override the name for the notebook, the image used, and the password,
you can pass template parameters using the ``--param`` option.

::

    oc new-app --template jupyter-notebook \
      --param APPLICATION_NAME=mynotebook \
      --param NOTEBOOK_IMAGE=jupyter/scipy-notebook:latest \
      --param NOTEBOOK_PASSWORD=mypassword

You can deploy any of the Jupyter Project docker-stacks images.

* jupyter/base-notebook
* jupyter/r-notebook
* jupyter/minimal-notebook
* jupyter/scipy-notebook
* jupyter/tensorflow-notebook
* jupyter/datascience-notebook
* jupyter/pyspark-notebook
* jupyter/all-spark-notebook

If you don't care what version of the image is used, add the ``:latest``
tag at the end of the image name, otherwise use the hash corresponding to
the image version you want to use.
