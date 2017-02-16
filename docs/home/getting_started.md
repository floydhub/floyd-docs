This page will walk you through running your first project on Floyd. We will train a 
convolutional neural network (CNN) model for handwritten digit recognition using the MNIST database. 
For more information on this, visit [Tensorflow's tutorial](https://www.tensorflow.org/versions/r0.10/tutorials/mnist/pros/).
We will be using Tensorflow but Floyd 
supports a wide variety of other popular [deep learning frameworks](environments.md) also.

## Installing Floyd CLI 

Floyd CLI is a python based command line tool to interact with FloydHub.

`floyd-cli` is available on [pypi](https://pypi.python.org/pypi/floyd-cli) and
runs on both Python 2.7 and Python 3.5.

Use pip to install the cli.

```bash
pip install -U floyd-cli
```

You can view the commands supported by the CLI using the `--help` option.

```bash
$ floyd --help
Usage: floyd [OPTIONS] COMMAND [ARGS]...

  Floyd CLI interacts with Floyd server and executes your commands. More
  help is available under each command listed below.

...
```

Detailed documentation for the floyd commands is available in the [documentation](../commands/index.md).

## Create an account

If you do not have an account already, visit the Floyd [website](https://www.floydhub.com/)
to create one.

## Login to Floyd

You can now use the command line to [login](../commands/login.md) to Floyd.

```bash
$ floyd login
Access token page will now open in your browser. Continue? [Y/n]:
Please paste the code here:
Login Successful
```

## Creating a new project

We will clone a [tensorflow-examples](https://github.com/floydhub/tensorflow-examples) repository. Alternatively, 
you can use any of your own projects you want to run on Floyd.

```bash
$ git clone https://github.com/floydhub/tensorflow-examples.git
Cloning into 'tensorflow-examples'...
$ cd tensorflow-examples/3_NeuralNetworks
```

Now initialize a new Floyd project with the [init](../commands/init.md) command and 
choose a project name.

```bash
$ floyd init first_proj
Project "first_proj" initialized in current directory
```

Now you are ready to run your first project on Floyd!

## Running your project on Floyd

Running your project on Floyd is simple. It is very similar to running code 
on your computer. Instead, the CLI syncs your code to Floyd servers and 
runs it on the cloud. Lets train and test a tensorflow implementation of 
handwriting digit recognition with MNIST dataset.

Use the floyd [run](../commands/run.md) command to run the code.

```bash
$ floyd run "python 2_BasicModels/nearest_neighbor.py" 
Syncing code ...
RUN ID                  NAME                      VERSION
----------------------  ---------------- 	 ---------
AKpnXqj9BEU6d8KhmygTyb  alice/first_proj:1         2
...
```

Congratulations! Your first experiment is now running on Floyd. 

## Checking run status

To see the status of your project runs, use the [status](../commands/status.md) command. You can specify 
a single `RUN ID` to get its status. Or the CLI will show the results of all your experiments 
in that project.

```bash
RUN ID                  CREATED        STATUS    DURATION(s)  NAME                INSTANCE     VERSION
----------------------  ---------      --------  -----------  ------------------- ---------   --------
AKpnXqj9BEU6d8KhmygTyb  just now       running            13  alice/first_proj:1  cpu                2
mBDHCqro9Hd2dHTYdRReGd  4 minutes ago  success           426  alice/tf-demo:1     cpu                1
```

## Viewing logs

You can view the logs of the experiment you just kicked off with the 
[logs](../commands/logs.md) command. You need to pass the `RUN ID` from the 
previous step to get the logs.

```bash
$ floyd logs AKpnXqj9BEU6d8KhmygTyb
...
##############################################################################

2017-02-15 22:25:20,315 INFO - Run Output:
...
2017-02-15 22:25:26,540 INFO - Test 0 Prediction: 7 True Class: 7
2017-02-15 22:25:26,555 INFO - Test 1 Prediction: 2 True Class: 2
2017-02-15 22:25:26,569 INFO - Test 2 Prediction: 1 True Class: 1
....
2017-02-15 22:25:29,783 INFO - Done!
2017-02-15 22:25:29,784 INFO - Accuracy: 0.9200000000000007
2017-02-15 22:25:29,942 INFO - 
##############################################################################
...
```

You can see the output of your code in the `Run Output` section of the logs.
Any thing you log or print in your code will appear here.

## Iterating on your project

If you would like to edit your code an re-run your project, you just use the `run`
command again. The CLI will upload the new version of your code and start another 
run of your project.
