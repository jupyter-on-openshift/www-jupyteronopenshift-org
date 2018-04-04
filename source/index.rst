Jupyter on OpenShift
====================

.. toctree::
   :maxdepth: 2
   :caption: Contents:

The Jupyter on OpenShift project provides you with the instructions you
need to be able to successfully deploy Jupyter notebooks on OpenShift_. This
could be a single Jupyter notebook instance, or a teaching/research
environment for more than one user, using JupyterHub to manage user access
and spawning of Jupyter notebooks.

*Note that this site is still in the process of being populated with
everything. Keep checking back for new content as it is added.*

.. _OpenShift: https://www.openshift.org/

What is Provided?
-----------------

A sample of what is provided by the Jupyter on OpenShift project is as
follows:

* Templates for deploying the Jupyter notebook images created by the
  Jupyter Project team.

* Source-to-Image (S2I) builder scripts for creating custom Jupyter
  notebook images based on those from the Jupyter Project team.

* Source code and templates for building and deploying a base Jupyter
  notebook image in OpenShift using the supported Python base images
  provided by your OpenShift environment. This image is S2I enabled and can
  also be used to build custom Jupyter notebook images, including just the
  Python packages you need, as well as notebook and data files.

* Source code and templates for building and deploying JupyterHub to
  OpenShift. This image is S2I enabled and can be customized using the S2I
  process to extend it with your own custom configurations, such as
  specifying the authentication provider you need to use, or adding form
  options to allow users to select the Jupyter notebook image to use.

A range of example deployments and configurations is also provided
including custom deployments for Jupyter notebooks, JupyterHub, notebook
viewer, kernel gateways and more.

Check out the table of contents for everything that is provided.

Why use OpenShift?
------------------

OpenShift is a platform to help you develop and deploy applications to one
or more hosts. These can be public facing web applications, or backend
applications, including micro services or databases. Applications can be
implemented in any programming language you choose. The only requirement is
that the application can run within a container.

In terms of cloud service computing models, OpenShift implements the
functionality of both a Platform as a Service (PaaS) and a Container as a
Service (CaaS).

OpenShift is implemented on top of Kubernetes, with Kubernetes implementing
the support for automating deployment, scaling and management of
containerized applications. Kubernetes provides the CaaS component of
OpenShift.

Kubernetes alone does not provide any support for building the container
image it runs. If using Kubernetes, you need to run a build tool to create
your application image on a separate system and push that to an image
registry from which it can be deployed. This is because CaaS focuses on
just running containers.

OpenShift builds on top of Kubernetes to implement the PaaS environment
which is more friendly to developers, as well as provide the additional
tools and services needed by operations to implement a comprehensive
container application platform.

Using the functionality of both Kubernetes and OpenShift simplifies your
ability to create custom deployments of Jupyter notebooks, JupyterHub and
other applications which are a part of the Jupyter ecosystem. OpenShift
provides a more friendly environment so you can deploy your applications
as a normal end user of the platform. You do not need administrator access,
nor need to know how to administer the platform.
