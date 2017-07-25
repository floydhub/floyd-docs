### Can I switch between Python 2 and Python 3 environments?

Most of our Python based [environments](../guides/environments.md) support both Python 2 and Python 3.

The default environments are Python 3. But you can use Python 2 by using the `:py2` tag with the environment name, when available. For example,

- Tensorflow 1.2 with Python 3
```bash
$ floyd run --env tensorflow-1.2
```

- Tensorflow 1.2 with Python 2
```bash
$ floyd run --env tensorflow-1.2:py2
```

We currently have Python 2 and 3 environments for Tensorflow, Theano, Caffe, PyTorch and Chainer. Please see our [complete list of environments](../guides/environments.md) for more details on the `--env` name.