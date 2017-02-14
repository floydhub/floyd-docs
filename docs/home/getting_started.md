This page will walk you through running your first project on Floyd. 
We will be using Tensorflow but Floyd 
can be used for a wide range of [frameworks](environments.md).

## Installing Floyd CLI 

Floyd CLI is a python based command line tool to interact with Floyd.

`floyd-cli` is available on [pypi](https://pypi.python.org/pypi/floyd-cli) and
runs on both Python 2.7 and Python 3.5.

Use pip to install the cli.

```bash
pip install -U floyd-cli
```

You can view the command supported by the CLI using the `--help` option.

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

Clone any tensorflow project you want to run on Floyd.

```bash
$ git clone https://github.com/floydhub/tensorflow-examples.git
Cloning into 'tensorflow-examples'...
$ cd tensorflow-examples
```

Now initialize a new Floyd project with the [init](../commands/init.md) command and 
choose a project name.

```bash
$ floyd init mnist
Project "mnist" initialized in current directory
```

Now you are ready to run your first project on Floyd!

## Running your project on Floyd

Running your project on Floyd is simple. It is very similar to running code 
on your computer. Instead, the CLI syncs your code to Floyd servers and 
runs it on the cloud. Lets train and test a tensorflow implementation of 
handwriting digit recognition with MNIST dataset.

Use the floyd [run](../commands/run.md) command to run the code.

```bash
$ floyd run "python train_tf.py -lr 0.01 -output /output/model.bin"
Syncing code ...
RUN ID                  NAME                           VERSION
----------------------  ---------------------------  ---------
dTe2cJJrNR2CBD74rSZXPA  floydhub/tensorflow-project:7        7
...
```

Congratulations! your first experiment is now running on Floyd. 

## Viewing logs

You can view the logs of the experiment you just kicked off with the 
[logs](../commands/logs.md) command. You need to pass the `RUN ID` from the 
previous step to get the logs.

```bash
$ floyd logs dTe2cJJrNR2CBD74rSZXPA
...
################################################################################

2017-01-20 19:18:41,353 INFO - Run Output:
2017-01-20 19:18:42,306 INFO - Epoch: 0001 cost= 0.200682446
2017-01-20 19:18:42,447 INFO - Epoch: 0002 cost= 0.165553480
...
################################################################################
...
```

You can see the output of your code in the `Run Output` section of the logs.
Any thing you log or print in your code will appear here.

## Checking run status

To see the status of your project runs, use the [status](../commands/status.md) command. You can specify 
a single `RUN ID` to get its status. Or the CLI will show the results of all your experiments 
in that project.

```bash
$ floyd status
RUN ID                  CREATED        STATUS      DURATION  NAME               INSTANCE      VERSION
----------------------  -------------  --------  ----------  -----------------  ----------  ---------
ncGPzDrm7XV58pBeKGUxd6  just now       success            3  alice/tf-demo:2     cpu                 2
mBDHCqro9Hd2dHTYdRReGd  4 minutes ago  success            4  alice/tf-demo:1     cpu                 1
```

## Iterating on your project

If you would like to edit your code an re-run your project, you just use the `run`
command again. The CLI will upload the new version of your code and start another 
run of your project.
