# Environments

Below is the list of Deep Learning environments supported by Floyd. Any of 
these can be specified in the floyd [run](../commands/run.md) command using the `--env` option.

If no `--env` is provided, it uses the `keras` image, which comes with a Python 3 image containing 
Keras 2.0.4 and Tensorflow 1.1.0 pre-installed.

| Framework | Env name (--env parameter)  |  Description              | Docker Image |
| --------- | ------------------ | ------------------------ |-------------|
| Tensorflow 1.1 | tensorflow  | Tensorflow 1.1.0 + Keras 2.0.4 on Python3. | [floydhub/tensorflow:1.1.0-py3](https://hub.docker.com/r/floydhub/tensorflow/) | 
| | tensorflow:py2  | Tensorflow 1.1.0 + Keras 2.0.4 on Python2. | [floydhub/tensorflow:1.1.0-py2](https://hub.docker.com/r/floydhub/tensorflow/) | 
| Tensorflow 1.0 | tensorflow-1.0  | Tensorflow 1.0.0 + Keras 1.2.2 on Python3. | [floydhub/tensorflow:1.0.0-py3](https://hub.docker.com/r/floydhub/tensorflow/) | 
| | tensorflow-1.0:py2  | Tensorflow 1.0.0 + Keras 1.2.2 on Python2. | [floydhub/tensorflow:1.0.0-py2](https://hub.docker.com/r/floydhub/tensorflow/) | 
| Tensorflow 0.12 | tensorflow-0.12  | Tensorflow 0.12.1 + Keras 1.2.2 on Python3. | [floydhub/tensorflow:0.12.1-py3](https://hub.docker.com/r/floydhub/tensorflow/) | 
| | tensorflow-0.12:py2  | Tensorflow 0.12.1 + Keras 1.2.2 on Python2. | [floydhub/tensorflow:0.12.1-py2](https://hub.docker.com/r/floydhub/tensorflow/) | 
| Theano | theano  | Theano rel-0.8.2 + Keras 1.2.2 on Python3. | [floydhub/theano:latest-py3](https://hub.docker.com/r/floydhub/theano/) | 
| | theano:py2  | Theano rel-0.8.2 + Keras 1.2.2 on Python2. | [floydhub/theano:latest-py2](https://hub.docker.com/r/floydhub/theano/) | 
| Keras | -  | Use tensorflow or theano for the appropriate Keras backend |  | 
| Caffe | caffe  | Caffe rc4 on Python3. | [floydhub/caffe:latest-py3](https://hub.docker.com/r/floydhub/caffe/) | 
| | caffe:py2  | Caffe rc4 on Python2. | [floydhub/caffe:latest-py2](https://hub.docker.com/r/floydhub/caffe/) | 
| Torch | torch | Torch 7 with Python 3 env. | [floydhub/torch:latest-py3](https://hub.docker.com/r/floydhub/torch/) | 
| | torch:py2 | Torch 7 with Python 2 env. | [floydhub/torch:latest-py2](https://hub.docker.com/r/floydhub/torch/) |
| PyTorch | pytorch | PyTorch 0.1.9 on Python 3. | [floydhub/pytorch:latest-py3](https://hub.docker.com/r/floydhub/pytorch/) | 
| | torch:py2 | PyTorch 0.1.9 on Python 2. | [floydhub/pytorch:latest-py2](https://hub.docker.com/r/floydhub/pytorch/) |
| Chainer (beta) | chainer | Chainer 1.21.0 on Python 3. | [floydhub/chainer:latest-py3](https://hub.docker.com/r/floydhub/chainer/) | 
| | chainer:py2 | Chainer 1.21.0 on Python 2. | [floydhub/chainer:latest-py2](https://hub.docker.com/r/floydhub/chainer/) |
| MxNet (beta) | mxnet:py2 | MxNet 0.9.3a on Python 2. | [floydhub/mxnet:latest-py2](https://hub.docker.com/r/floydhub/mxnet/) |
| Kur | kur | Kur 0.3.0 on Python 3. | [floydhub/kur:latest-py3](https://hub.docker.com/r/floydhub/kur/) |

All environments are available for both CPU and GPU execution. For example, 

To run a Tensorflow job on CPU
```bash
$ floyd run --env tensorflow:py2 "python mnist_cnn.py" 
```

To run a Tensorflow job on GPU (CUDA, cuDNN, etc. installed)
```bash
$ floyd run --env tensorflow:py2 --gpu "python mnist_cnn.py" 
```

The following software packages (in addition to many other common libraries) are available in all the environments:
```
h5py, iPython, Jupyter, matplotlib, numpy, OpenCV, Pandas, Pillow, scikit-learn, scipy, sklearn
```

{!contributing.md!}
