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

#### Install Jupyterlab
`(project) $pip3 install jupyterlab`<br/>

#### Install Jupyter Notebook
`(project) $pip3 install jupyter`<br/>

`(project) $python3 -m pip install jupyter`<br/>

#### Test Jupyter Installation
`(project) $which python3`<br/>
`(project) $which ipython3`<br/>
`(project) $which jupyter-notebook`<br/>

#### Find jupter version
```
$jupyter --version
```
![https://github.com/lel99999/dev_JupyterRH7/blob/master/jupyter_version-02.png](https://github.com/lel99999/dev_JupyterRH7/blob/master/jupyter_version-02.png) <br/>

#### Save or Freeze the requirements
`$pip list`  Will list all packages <br/>
`$pip freeze > requirements.txt`<br/>
This will create a list containing all the packages in current environment, and their versions.<br/>
To recreate the same environment and install same packages:<br/>
`$pip3 install -r requirements.txt`<br/>


#### After Jupyter Install Launch Jupyter Notebook:
`$jupyter notebook`<br/>

#### Setup Jupyter Notebook Proxy

#### IJavascript - Javascript Kernel for Jupyter Notebook
[https://github.com/n-riesco/ijavascript](https://github.com/n-riesco/ijavascript) <br/>

#### Connect in Windows with Putty
- Jupyter runs on port 8888
- Open putty <br/>
  ![Open Putty](https://github.com/lel99999/dev_JupyterRH7/blob/master/putty-01.PNG) <br/>

  - in Connection -> SSH -> Tunnels :: Add new forwarded port
  - set Source port: 8888
  - set Destination: localhost:8888
  - click Add button <br/>
  ![https://github.com/lel99999/dev_JupyterRH7/blob/master/putty-03.PNG](https://github.com/lel99999/dev_JupyterRH7/blob/master/putty-03.PNG) <br/>
  
  - click Open button
  - Login, then go to your home folder/notebooks folder and launch Jupyter
```
$jupyter notebook --no-browser
```

#### Adding Kernels
- Within a Jupyter Notebook
  ```
  !python2 -V
  !python2 -m pip install ipykernel
  !python2 -m ipykernel install --user
  ```
  
  Anaconda/Conda/Miniconda <br/>
  ```
  !conda create -n py27 python=2.7
  !conda activate py27
  !conda install notebook ipykernel
  !ipython kernel install --user
  ```

#### Making Kernels for Jupyter
- [https://jupyter-client.readthedocs.io/en/stable/kernels.html](https://jupyter-client.readthedocs.io/en/stable/kernels.html) <br/>

#### Explore Dynamic Kernels for Jupyter
- Multiple Kernels in One Jupyter Notebook
  - [https://vatlab.github.io/sos-docs/doc/user_guide/multi_kernel_notebook.html](https://vatlab.github.io/sos-docs/doc/user_guide/multi_kernel_notebook.html) <br/>

#### Adding Kernels
- Custom Virtualenv
  ```
  ## activate virtualenv
  $source custom-venv/bin/activate

  ## install jupyter in the virtualenv
  $(custom-venv)$pip install jupyter

  ## add virtualvenv as jupyter kernel
  (custom-venv)$ipython kernel install --name "custom-venv" --user
  ```
- Spark Kernel (prerequisite: Java and local Spark installation)
  ```
  $pip install jupyter
  $pip install --upgrade toree
  $jupyter toree install --user --spark_home=/<path>/spark-2.4.8-bin-hadoop2.7
  $jupyter notebook  ## select Apache Toree -Scala
  ```
- Scala Kernel
  ```
  ## Download almond and scala libs (coursier is a scala tool to install almond)
  $curl -Lo coursier https://git.io/coursier-cli && chmod +x coursier

  ## update/replace scala and almond versions if need be
  $ ./coursier bootstrap \
    -r jitpack \
    -i user -I user:sh.almond:scala-kernel-api_2.12.11:0.10.0 \
    sh.almond:scala-kernel_2.12.11:0.10.0 \
    -o almond

  ## install scala kernel in jupyter
  $./almond --install --id scala_2_12_11  --display-name "Scala 2.12.11"

  ## open jupyter notebook and select Scala kernel
  $jupyter notebook
  ```
- List kernels
  `$jupyter kernelspec list` <br/>

- Remove kernel
  `$jupyter kernelspec remove <kernel_name>` <br/>

#### BUild Dockerfile 
`$docker build - < <Dockerfile.XXX>` <br/>
