Deleting the Notebook Instance
------------------------------

To delete the notebook instance, run ``oc delete`` using a label selector
for the application name.

::

  oc delete all,configmap --selector app=mynotebook
