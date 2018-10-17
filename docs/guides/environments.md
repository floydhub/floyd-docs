# Environments

Below is the list of Deep Learning environments supported by FloydHub. Any of
these can be specified in the floyd [run](../commands/run.md) command using the
`--env` option.

If no `--env` is provided, it uses the `tensorflow-1.8` image by default, which comes with Python
3.6, Keras 2.1.6 and Tensorflow 1.8.0 pre-installed.

| Framework | Env name (--env parameter)  |  Description              | Docker Image | Packages and Nvidia Settings
| --------- | --------------------------- | ------------------------- |------------- | ------------------------ |
| Tensorflow 1.11 | tensorflow-1.11  | Tensorflow 1.11.0 + Keras 2.2.4 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) | [Tensorflow-1.11](./tensorflow.md#tensorflow-111)
|                | tensorflow-1.11:py2  | Tensorflow 1.11.0 + Keras 2.2.4 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.10 | tensorflow-1.10  | Tensorflow 1.10.0 + Keras 2.2.0 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) | [Tensorflow-1.10](./tensorflow.md#tensorflow-110)
|                | tensorflow-1.10:py2  | Tensorflow 1.10.0 + Keras 2.2.0 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.9 | tensorflow-1.9  | Tensorflow 1.9.0 + Keras 2.2.0 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) | [Tensorflow-1.9](./tensorflow.md#tensorflow-19)
|                | tensorflow-1.9:py2  | Tensorflow 1.9.0 + Keras 2.2.0 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.8 | tensorflow-1.8  | Tensorflow 1.8.0 + Keras 2.1.6 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) | [Tensorflow-1.8](./tensorflow.md#tensorflow-18)
|                | tensorflow-1.8:py2  | Tensorflow 1.8.0 + Keras 2.1.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.7 | tensorflow-1.7  | Tensorflow 1.7.0 + Keras 2.1.6 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) | [Tensorflow-1.7](./tensorflow.md#tensorflow-17)
|                | tensorflow-1.7:py2  | Tensorflow 1.7.0 + Keras 2.1.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.5 | tensorflow-1.5  | Tensorflow 1.5.0 + Keras 2.1.6 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) | [Tensorflow-1.5](./tensorflow.md#tensorflow-15)
|                | tensorflow-1.5:py2  | Tensorflow 1.5.0 + Keras 2.1.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.4 | tensorflow-1.4  | Tensorflow 1.4.0 + Keras 2.0.8 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
|                | tensorflow-1.4:py2  | Tensorflow 1.4.0 + Keras 2.0.8 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.3 | tensorflow-1.3  | Tensorflow 1.3.0 + Keras 2.0.6 on Python 3.6. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
|                | tensorflow-1.3:py2  | Tensorflow 1.3.0 + Keras 2.0.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.2 | tensorflow-1.2  | Tensorflow 1.2.0 + Keras 2.0.6 on Python 3.5. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
|                | tensorflow-1.2:py2  | Tensorflow 1.2.0 + Keras 2.0.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.1 | tensorflow  | Tensorflow 1.1.0 + Keras 2.0.6 on Python 3.5. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
|                | tensorflow:py2  | Tensorflow 1.1.0 + Keras 2.0.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 1.0 | tensorflow-1.0  | Tensorflow 1.0.0 + Keras 2.0.6 on Python 3.5. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
|                | tensorflow-1.0:py2  | Tensorflow 1.0.0 + Keras 2.0.6 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| Tensorflow 0.12 | tensorflow-0.12  | Tensorflow 0.12.1 + Keras 1.2.2 on Python 3.5. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
|                 | tensorflow-0.12:py2  | Tensorflow 0.12.1 + Keras 1.2.2 on Python 2. | [floydhub/tensorflow](https://hub.docker.com/r/floydhub/tensorflow/) |
| PyTorch 1.0 (preview) | pytorch-1.0     | PyTorch 1.0.0 + fastai 1.0.4 on Python 3.6. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) | [PyTorch-1.0](./pytorch.md#pytorch-10-preview)
|             | pytorch-1.0:py2 | PyTorch 1.0.0 + fastai 1.0.4 on Python 2. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
| PyTorch 0.4 | pytorch-0.4     | PyTorch 0.4.1 on Python 3.6. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) | [PyTorch-0.4](./pytorch.md#pytorch-04)
|             | pytorch-0.4:py2 | PyTorch 0.4.1 on Python 2. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
| PyTorch 0.3 | pytorch-0.3     | PyTorch 0.3.1 on Python 3.6. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) | [PyTorch-0.3](./pytorch.md#pytorch-03)
|             | pytorch-0.3:py2 | PyTorch 0.3.1 on Python 2. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
| PyTorch 0.2 | pytorch-0.2     | PyTorch 0.2.0 on Python 3.5 | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
|             | pytorch-0.2:py2 | PyTorch 0.2.0 on Python 2. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
| PyTorch 0.1 | pytorch-0.1     | PyTorch 0.1.12 on Python 3. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
|             | pytorch-0.1:py2 | PyTorch 0.1.12 on Python 2. | [floydhub/pytorch](https://hub.docker.com/r/floydhub/pytorch/) |
| Theano 0.9 | theano-0.9  | Theano rel-0.8.2 + Keras 2.0.3 on Python3.5. | [floydhub/theano](https://hub.docker.com/r/floydhub/theano/) |
|            | theano-0.9:py2  | Theano rel-0.8.2 + Keras 2.0.3 on Python2. | [floydhub/theano](https://hub.docker.com/r/floydhub/theano/) |
| Caffe | caffe  | Caffe rc4 on Python3.5. | [floydhub/caffe](https://hub.docker.com/r/floydhub/caffe/) |
|       | caffe:py2  | Caffe rc4 on Python2. | [floydhub/caffe](https://hub.docker.com/r/floydhub/caffe/) |
| Torch | torch | Torch 7 with Python 3 env. | [floydhub/torch](https://hub.docker.com/r/floydhub/torch/) |
|       | torch:py2 | Torch 7 with Python 2 env. | [floydhub/torch](https://hub.docker.com/r/floydhub/torch/) |
| Chainer 1.23 | chainer-1.23 | Chainer 1.23.0 on Python 3. | [floydhub/chainer](https://hub.docker.com/r/floydhub/chainer/) |
|              | chainer-1.23:py2 | Chainer 1.23.0 on Python 2. | [floydhub/chainer](https://hub.docker.com/r/floydhub/chainer/) |
| Chainer 2.0 | chainer-2.0 | Chainer 1.23.0 on Python 3. | [floydhub/chainer](https://hub.docker.com/r/floydhub/chainer/) |
|             | chainer-2.0:py2 | Chainer 1.23.0 on Python 2. | [floydhub/chainer](https://hub.docker.com/r/floydhub/chainer/) |
| MxNet 1.0 | mxnet | MxNet 1.0.0 on Python 3.6. | [floydhub/mxnet](https://hub.docker.com/r/floydhub/mxnet/) |
|           | mxnet:py2 | MxNet 1.0.0 on Python 2. | [floydhub/mxnet](https://hub.docker.com/r/floydhub/mxnet/) |

All environments are available for both CPU and GPU execution. For example,

To run a Python2 Tensorflow job on CPU
```bash
$ floyd run --env tensorflow:py2 "python mnist_cnn.py"
```

To run a Python2 Tensorflow job on GPU (CUDA, cuDNN, etc. installed)
```bash
$ floyd run --env tensorflow:py2 --gpu "python mnist_cnn.py"
```

The following software packages (in addition to many other common libraries) are available in all the environments:
```
h5py, iPython, Jupyter, matplotlib, numpy, OpenCV, Pandas, Pillow, scikit-learn, scipy, sklearn
```

{!contributing.md!}
