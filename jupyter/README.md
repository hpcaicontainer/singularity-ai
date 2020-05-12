# Jupyter Container
The container has one **condaenv** which includes: 

- Jupyter 
- Tensorflow, 
- Keras, 
- Opencv, 
- Matplotlib, 
- Pandas, 
- Scikit-learn, 
- R
- R-essentials

When you use it first time, you can clone  **condaenv** in the container to the mounted home directory, such as **~/conda_env**,   then start jupyter. If you install python libraries through jupyter, these installed libraries are under **~/conda_env**.

```
singularity shell jupyter27.simg

export conda_env=~/conda_env
export password=mypassword
export workdir=~/myworkdir

conda create -y -v --clone $IMAGE_CONDA_ENV -p $conda_env

source activate $conda_env

jupyter notebook --no-browser --ip=0.0.0.0 --port=5901 --NotebookApp.port_retries=0 \
--NotebookApp.password=$password --NotebookApp.notebook_dir=$workdir \
--ContentsManager.root_dir=$conda_env --NotebookApp.allow_origin='*' --   NotebookApp.allow_remote_access=True \
--NotebookApp.disable_check_xsrf=True --allow-root
```

When you use it next time, you don't need clone again, just source the existing **~/conda_env**， the installed libraries before are still being there.

```
singularity shell jupyter27.simg

export conda_env=~/conda_env
export password=mypassword
export workdir=~/myworkdir

source activate $conda_env

jupyter notebook --no-browser --ip=0.0.0.0 --port=5901 --NotebookApp.port_retries=0 \
--NotebookApp.password=$password --NotebookApp.notebook_dir=$workdir \
--ContentsManager.root_dir=$conda_env --NotebookApp.allow_origin='*' --   NotebookApp.allow_remote_access=True \
--NotebookApp.disable_check_xsrf=True --allow-root
```

