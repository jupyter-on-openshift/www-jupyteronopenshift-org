Issues with File Permissions
----------------------------

The reason that the Jupyter Project images will not run out of the box on
OpenShift, is that OpenShift is a multitenant environment designed for use
by many users at the same time. For this reason, applications in different
projects are by default assigned a unique user ID under which they need to
run. This overrides what the application image says it wants to run as. As
a result, when the Jupyter notebook application starts, it is unable to
write files to the container file system, as it doesn't have the required
permissions.

The issue with the Jupyter Project images is that they are designed to
normally be run as a hard wired user ID. Permissions of directories and
files in that image are set such that they can only be written to by the
user ID the image wants to be run as, or any user in the group ``users``.

When the Jupyter notebook images are run under OpenShift, the user ID they
are required to run as, has a very high user ID for which there is no entry
in the ``/etc/passwd`` file of the image. Because there is no entry, this
results in the group ID used being ``root``. As a consequence, the running
application cannot write files to the container filesystem, as it is neither
running as the correct user ID, or in the correct group.

One could override the security measures enforced by OpenShift and allow
the image to run as user ID it wants to, but this will not be possible if
you don't have administrator access to the OpenShift platform.

The better workaround is to instruct OpenShift when running the image,
to configure the container such that the user runs with a supplemental
group with group ID of ``100``, corresponding to the ``users`` group. With
this set, the application can then write to the container filesystem.
