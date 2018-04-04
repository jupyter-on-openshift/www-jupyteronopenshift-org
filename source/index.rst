Jupyter on OpenShift
====================

.. toctree::
   :maxdepth: 2
   :caption: Contents:

The Jupyter on OpenShift project provides software and instructions to help
you run Jupyter notebooks and JupyterHub on OpenShift.

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
a system for automating deployment, scaling and management of containerized
applications. Kubernetes provides the Container as a Service (CaaS)
component of OpenShift.

Kubernetes alone does not provide any support for building the container
image it runs. You need to run a build tool to create your application
image on a separate system and push that to an image registry from which it
can be deployed. This is because CaaS focuses on just running containers.

OpenShift builds on top of Kubernetes to implement a Platform as Service
(PaaS) environment which is more friendly to developers, as well as provide
the additional tools and services needed by operations to implement a
comprehensive container application platform.

Using the functionality of both Kubernetes and OpenShift simplifies your
ability to create custom deployments of Jupyter notebooks, JupyterHub and
other applications which are a part of the Jupyter ecosystem. OpenShift
provides a more friendly environment so you can deploy your applications
as a normal end user of the platform. You do not need administrator access,
nor need to know how to administer the platform.
