Deploying a Custom Image
------------------------

If you want to deploy a custom variant of the Jupyter Project images, you
can replace the image name with that of your own. If the image is not
stored on Docker Hub, but some other public image registry, prefix the name
of the image with the image registry host details.

If the image is in your OpenShift project, because you imported the image
into OpenShift, or used the docker build strategy of OpenShift to build a
derived custom image, you can use the name of the image stream for the
image name, including any image tag if necessary.

This can be illustrated by first importing an image into the OpenShift
project.

::

    oc import-image jupyter/datascience-notebook:latest --confirm

Then deploy it using the name of the image stream created.

::

    oc new-app --template jupyter-notebook \
      --param APPLICATION_NAME=mynotebook \
      --param NOTEBOOK_IMAGE=datascience-notebook \
      --param NOTEBOOK_PASSWORD=mypassword

Importing an image into OpenShift before deploying it means that when a
notebook is started, the image need only be pulled from the internal
OpenShift image registry rather than Docker Hub for each deployment.
Because the images are so large, this can speed up deployments when the
image hasn't previously been deployed to a node in the OpenShift cluster.
