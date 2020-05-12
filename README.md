# AI Containers
This repository includes the singularity container definition file for common used AI frameworks and Dev tools.

- Caffe
- Tensorflow, 
- MXNet 
- PyTorch, 
- Chainer, 
- Scikit, 
- Jupyter

You need cd to the directory and build singularity images, such as:

```
cd caffe
singularity build caffe.simg caffe-1.0-cpu.sif
```

We will continue to update and add more container.