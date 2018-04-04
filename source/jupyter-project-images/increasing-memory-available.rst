Increasing Memory Available
---------------------------

The template provided does not specify how much memory should be made
available to the notebook. In an OpenShift cluster where quotas are
enforced, the default memory limit per container will be applied. This
is typically 512Mi.

If you need to increase the amount of memory available to the container,
you can run the command::

    oc set resources dc/notebook --limits memory=1Gi

Note that when you open a notebook and a new kernel created, it is created
as a sub process in the same container, so opening multiple notebooks at
the same time will increase memory usage. Open too many and you may hit the
limit imposed when a quiota is in place.
