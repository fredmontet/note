DVC
===

Stands for Data Version Control

Initialiye DVC
--------------

    dvc init

Add a file or folder
--------------------

    dvc add <path>

Store data remotely on a remote server
--------------------------------------

With Google Drive

    dvc remote add -d remote gdrive://1ynNBbT-4J0ida0eKYQqZZbC93juUUbVHi

With S3/Minio

    dvc remote add -d myrepo s3://mybucket

-d stands for default. The information about the storage will be saved under .dvc/config

Push the data to the remote
---------------------------

    dvc push

Get the data from the remote
----------------------------

    dvc pull

Switch from one version of the data to another
----------------------------------------------

    git checkout <commit id>
    dvc checkout

if you want to save the changes

    git commit data.dvc -m "revert to previous version"

References
----------

- https://towardsdatascience.com/introduction-to-dvc-data-version-control-tool-for-machine-learning-projects-7cb49c229fe0
- https://dvc.org/

