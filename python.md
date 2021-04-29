Python
======

Work on a Package
-----------------

### Install a package from the current directory in editable mode

	pip install -e .

This is the only way to develop a package a bit dynamically.


Virtual Environment
-------------------

### Create a new virtual environment

	python3 -m venv virtualenv

### Activate a virtual environment

	source virtualenv/bin/activate


Package Creation
----------------

https://packaging.python.org/tutorials/packaging-projects/

To make an update:
  - delete all files in the `dist` folder
  - update the version number in `setup.py` file

Re-create the wheels and re-upload the files by executing the two following command lines

### Generate the distribution archive (where setup.py is located)

	python3 setup.py sdist bdist_wheel

The output is in the `dist` folder.

### Upload the distribution archive to PyPi

	python3 -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*


Remove all packages
-------------------

No problem, here's the magic command

	pip freeze | xargs pip uninstall -y

And if you have some VCS packages

	pip freeze | grep -v "^-e" | xargs pip uninstall -y

