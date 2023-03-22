Jupyter
=======

## Make a kernel

When you are in your virtual env use the following command

    python -m ipykernel install --user --name=<my-kernel-name>
    
or

    ipython kernel install --name "<my-kernel-name>" --user

## Delete a kernel

Just delete the files according to the output of this command

    jupyter kernelspec list


