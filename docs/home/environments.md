# Environments

Below is the list of Deep Learning environments supported by Floyd. Any of 
these can be specified in the floyd [run](../commands/run.md) command using the `--env` option.

If no `--env` is provided, it uses the `keras` image, which comes with a Python 3 image containing 
Keras 1.2.2, Tensorflow 0.12.1 and Theano rel-0.8.2 pre-installed.

| Framework | Env name (--env parameter)  |  Description              | Docker Image |
| --------- | ------------------ | ------------------------ |-------------|
| Tensorflow | tensorflow  | Tensorflow 0.12.1 on Python3. | [floydhub/tensorflow:latest-py3](https://hub.docker.com/r/floydhub/tensorflow/) | 
| | tensorflow:py2  | Tensorflow 0.12.1 on Python2. | [floydhub/tensorflow:latest-py2](https://hub.docker.com/r/floydhub/tensorflow/) | 
| Keras | keras  | Keras 1.2.2 on Python3. | [floydhub/keras:latest-py3](https://hub.docker.com/r/floydhub/keras/) | 
| | keras:py2  | Keras 1.2.2 on Python2. | [floydhub/keras:latest-py2](https://hub.docker.com/r/floydhub/keras/) | 
| Theano | theano  | Theano rel-0.8.2 on Python3. | [floydhub/theano:latest-py3](https://hub.docker.com/r/floydhub/theano/) | 
| | theano:py2  | Theano rel-0.8.2 on Python2. | [floydhub/theano:latest-py2](https://hub.docker.com/r/floydhub/theano/) | 
| Torch (coming soon) |   |  | [floydhub/torch:latest-py3](https://hub.docker.com/r/floydhub/torch/) | 

All environments are available for both CPU and GPU execution. For example, 

To run a Tensorflow job on CPU
```bash
$ floyd run --env tensorflow:py2 "python mnist_cnn.py" 
```

To run a Tensorflow job on GPU (CUDA, cuDNN, etc. installed)
```bash
$ floyd run --env tensorflow:py2 --gpu "python mnist_cnn.py" 
```