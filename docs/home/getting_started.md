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

If you do not have an account already, visit the FloydHub [website](https://www.floydhub.com/)
to create one.

## Login to Floyd

You can now use the command line to [login](../commands/login.md) to Floyd.

```bash
$ floyd login
Authentication token page will now open in your browser. Continue? [Y/n]:
Please paste the token here:
Login Successful
```

Copy the authentication token from your browser (available after you login) and paste it in your terminal.

## Creating a new project

We will clone and use a [tensorflow-examples](https://github.com/floydhub/tensorflow-examples) repository. Alternatively, 
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
handwriting digit recognition using CNNs and the MNIST dataset.

Use the floyd [run](../commands/run.md) command to run the code.

```bash
$ floyd run --gpu "python mnist_cnn.py" 
Syncing code ...
RUN ID                  NAME                      VERSION
----------------------  ---------------- 	 ---------
AKpnXqj9BEU6d8KhmygTyb  alice/first_proj:1         2
...
```

Congratulations! Your first experiment is now running on Floyd. Behind the scenes, Floyd did the following:

* Synced your local code to the cloud
* Spun up a GPU instance (because `--gpu`)
* Setup an environment with Tensorflow installed
* Started executing your command inside this environment

Make note of the RUN_ID. You will be using this to issue additional commands related to your job.

## Training on CPU vs. GPU

When using the `floyd run` command, by default, a CPU machine is used to execute your job. If you 
want to use a GPU instance (Nvidia Tesla K80 with 12GB memory), use the `--gpu` flag.

To run job on CPU
```bash
$ floyd run "python mnist_cnn.py" 
```

To run job on GPU
```bash
$ floyd run --gpu "python mnist_cnn.py" 
```

## Checking run status

To see the status of your project runs, use the [status](../commands/status.md) command. You can specify 
a single `RUN ID` to get its status. Or the CLI will show the results of all your runs of the current  
project.

```bash
$ floyd status
RUN ID                  CREATED        STATUS    DURATION(s)  NAME                INSTANCE     VERSION
----------------------  ---------      --------  -----------  ------------------- ---------   --------
AKpnXqj9BEU6d8KhmygTyb  just now       running            13  alice/first_proj:1  gpu                2
mBDHCqro9Hd2dHTYdRReGd  4 minutes ago  success           426  alice/tf-demo:1     cpu                1
```

## Viewing logs

You can view the logs of the experiment you just kicked off with the 
[logs](../commands/logs.md) command. You need to pass the `RUN ID` from the 
previous step to get the logs. 

```bash
$ floyd logs AKpnXqj9BEU6d8KhmygTyb -t
...
##############################################################################

2017-02-15 22:25:20,315 INFO - Run Output:
...
2017-02-15 22:25:26,540 INFO - Iter 1280, Minibatch Loss= 19537.398438, Training Accuracy= 0.25781
2017-02-15 22:25:26,555 INFO - Iter 2560, Minibatch Loss= 8323.721680, Training Accuracy= 0.49219
2017-02-15 22:25:26,569 INFO - Iter 3840, Minibatch Loss= 7442.384766, Training Accuracy= 0.64844
....
2017-02-15 22:25:29,783 INFO - Optimization Finished!
2017-02-15 22:25:29,784 INFO - Testing Accuracy: 0.980469
2017-02-15 22:25:29,942 INFO - 
##############################################################################
...
```

You can see the output of your code in the `Run Output` section of the logs.
Any thing you log or print in your code will appear here. Using the `-t` (tail) flag 
streams the logs as they are generated.

## Iterating on your project

You can edit your code locally and re-run your project using the `run` command. 
The CLI will upload the new version of your code and start another 
run of your project. Floyd manages and keeps track of all revisions of your experiments.
