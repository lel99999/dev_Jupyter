# dev_JupyterRH7
Jupyter Integration for RHEL 7.x

#### Install virtualenv
`$pip3 install virtualenv`<br/>

#### Setup and Activate virtual environment
`virtualenv --system-site-packages -p python3 ~/<project>`<br/>
or<br/>

`$python3 -m venv /<path-to-projectt/`<br/>

`$source ~/<project>/bin/activate`<br/>
`$source /<path-to-environment/bin/activate`<br/>
`Should see: (project) $`<br/>

####pyenv was recommended tool for creating virtual environments for Python v3.3 & v3.4, but has been depreacted in v3.6

#### Install IPython
`(project) $pip3 install ipython`<br/>

#### Install Jupyter Notebook
`(project) $pip3 install jupiter`<br/>

`(project) $python3 -m pip install jupyter`<br/>

#### Test Jupyter Installation
`(project) $which python3`<br/>
`(project) $which ipython3`<br/>
`(project) $which jupyter-notebook`<br/>

#### Save or Freeze the requirements
`$pip list`  Will list all packages <br/>
`$pip freeze > requirements.txt`<br/>
This will create a list containing all the packages in current environment, and their versions.<br/>
To recreate the same environment and install same packages:<br/>
`$pip3 install -r requirements.txt`<br/>


#### After Jupyter Install Launch Jupyter Notebook:
`$jupyter notebook`<br/>
