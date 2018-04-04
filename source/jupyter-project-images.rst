======================
Jupyter Project Images
======================

The Jupyter Project team provides an official set of Jupyter notebook
images for running in container environments such as Docker and Kubernetes.
Although OpenShift can run the images, they will not run out of the box on
a standard OpenShift installation. To make it easier to run the images, a
template is provided which ensures the images are run with the correct
configuration.

.. include:: jupyter-project-images/available-notebook-images.rst
.. include:: jupyter-project-images/issues-with-the-images.rst
.. include:: jupyter-project-images/loading-the-templates.rst
.. include:: jupyter-project-images/deploying-a-notebook.rst
.. include:: jupyter-project-images/passing-template-parameters.rst
