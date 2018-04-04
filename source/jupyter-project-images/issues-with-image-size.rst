Issues with Image Size
----------------------

An additional issue with the Jupyter Project images when deploying to
OpenShift is the size of the images. The ``base-notebook`` image is
close to 3GB in size. This means they cannot be used on OpenShift
environments, such as OpenShift Online, which cap image/container
filesystem size at 3GB.

Part of the issue with the size of the Jupyter Project images appears to be
due to the use of the Ubuntu base image, the use of the Anaconda Python
distribution, and inclusion of packages such as Latex. These all combine to
create a very large image.

Even if the image size is below the cap for image/container filesystem
size, if it is only just below the limit, you may not be able to install
any additional Python packages due to lack of free space in the filesystem.
