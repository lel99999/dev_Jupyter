# dev_JupyterRH7
Jupyter Integration for RHEL 7.x

#### Install virtualenv
`$pip3 install virtualenv`<br/>

#### Setup and Activate virtual environment
`virtualenv --system-site-packages -p python3 ~/<project>
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
`(project) $which python3
