Adding Persistent Storage
-------------------------

You can upload notebooks and other files using the web interface of the
notebook. Any uploaded files or changes you make to them will be lost when
the notebook instance is restarted. If you want to save your work, you need
to add persistent storage to the notebook. To add persistent storage run::

    oc set volume dc/mynotebook --add \
	  --type=pvc --claim-size=1Gi --claim-mode=ReadWriteOnce \
	  --claim-name mynotebook-data --name data \
	  --mount-path /home/jovyan

When you have deleted the notebook instance, if using a persistent volume,
you will need to delete it in a separate step.

::

    oc delete pvc/mynotebook-data
