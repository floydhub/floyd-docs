In this quick start guide, we will walk you through running your first project on FloydHub. We will train a simple convolutional neural network (CNN) model to recognize handwritten digits using Tensorflow and the MNIST dataset. For more details on the data and the model, please refer to the [Tensorflow tutorial](https://www.tensorflow.org/get_started/mnist/pros).

## What we will accomplish in this guide

- Learn about FloydHub's web dashboard and `floyd-cli` tool
- Initialize an existing project on your computer
- Run a job using `floyd run` command to train your deep learning model on FloydHub's GPU servers
- View the logs and stored output

## Quick preparation checklist

- You must have a [FloydHub account](https://www.floydhub.com/login)
- You must have `floyd-cli` [installed on your computer](../guides/basics/install.md)
- You must [log in to FloydHub through the CLI](../guides/basics/login.md)


## Web dashboard and floyd-cli

FloydHub has a [web dashboard](https://www.floydhub.com/projects) and a [CLI](/guides/basics/install.md) that you can use to interact with FloydHub from your terminal. If you are familiar with Github, think of the CLI tool (`floyd` command) as the equivalent of the `git` command. You can initialize projects, run jobs, view logs and outputs, etc. all using the CLI. 

The web dashboard is useful for getting an overview of your work and exploring others' projects and datasets.

## Setup

### Get the code
We will clone the [quick-start repository](https://github.com/floydhub/quick-start) from Github and run it on FloydHub. 

```bash
$ git clone https://github.com/floydhub/quick-start.git
Cloning into 'quick-start'...
...
$ cd quick-start
```

```bash
$ ls
LICENSE    mnist_cnn.py    mnist_cnn.ipynb    README.md
```

This repository contains two main files: `mnist_cnn.py` (a Python script) and `mnist_cnn.ipynb` (a Jupyter Notebook). In this guide, we will use the Python script. We will explore running Jupyter Notebooks in our [next tutorial](/getstarted/quick_start_jupyter.md).

### Initialize project
If you are a new user, you should see a default project named `quick-start` in your [Projects dashboard](https://www.floydhub.com/projects).

![Quick start project](../img/quick_start_project.jpg)

If you don't see it, you can create a new project named `quick-start` and still follow through with the rest of this guide. See [instructions](../guides/basics/create_new/#create-a-new-project) to create a new project.

A [Project](../guides/core_concepts.md#projects) is a space for tackling a specific problem. It is a collection of jobs that you run, data, logs and results. If you have used GitHub, projects in FloydHub are a lot like code repositories.

To start using this project, initialize it in your current directory in your terminal. 

```bash
$ floyd init quick-start
Project "quick-start" initialized in the current directory
```

This tells Floyd that all the jobs you run from this directory belong to the project named `quick-start`.

## Running your first job on FloydHub

A [Job](../guides/core_concepts.md#jobs) is created when you execute a command inside a project on FloydHub.

Running a job on FloydHub is simple. It is very similar to running code on your local machine. Instead, when you use the `floyd run` command, the CLI syncs your code to the FloydHub's servers and runs it in the cloud. 

For this tutorial, we will run the `mnist_cnn.py` Python script on FloydHub's GPU servers.

```bash
$ floyd run --gpu --env tensorflow "python mnist_cnn.py"
Syncing code ...
RUN ID                  NAME               
----------------------  -------------------
AKpnXqj9BEU6d8KhmygTyb  alice/quick-start/1

To view the logs enter:
    floyd logs alice/quick-start/1
```

Congratulations! Your first job is now running on FloydHub's GPU. Behind the scenes, Floyd does the following:

- Sync your local code to FloydHub's server
- Provision a GPU instance on the cloud (because `--gpu`)
- Set up a deep learning environment with GPU drivers and Tensorflow installed (because `--env tensorflow`)
- Execute the command `python mnist_cnn.py` inside this environment
- Store the output logs and generated output data
- Terminate the GPU instance once the command finishes execution

## Next steps

### Check the status of your job

You can view the status of your job from your terminal using the [floyd status](../commands/status.md) command. You can specify a single job name (e.g. `floyd status alice/quick-start/1`) to get its status, or the CLI will show the status of all jobs in the current project.

```bash
$ floyd status
RUN ID                  CREATED        STATUS    DURATION(s)  NAME                 INSTANCE    DESCRIPTION
----------------------  ---------      --------  -----------  -------------------  ---------   -----------
AKpnXqj9BEU6d8KhmygTyb  just now       running            15  alice/quick-start:1  gpu         
```

You can also view the status of your job in your browser by visiting the `Job URL` printed by the `floyd run` command. For example, `www.floydhub.com/alice/quick-start/1`

![Job run](../img/job_run.jpg)

### View output logs

You can view the logs generated by the job from your terminal using the [floyd logs](../commands/logs.md) command. You need to specify the job name.

```bash
$ floyd logs -t alice/quick-start/1
...
2017-07-12 16:00:07,446 INFO - Starting attempt 1 at 2017-07-12 16:00:07.436349
2017-07-12 16:00:09,088 INFO - Starting container...
2017-07-12 16:00:09,297 INFO - 
...
##############################################################################
2017-07-12 16:00:09,297 INFO - Run Output:
2017-07-12 16:01:46,154 INFO - Successfully downloaded train-images-idx3-ubyte.gz 9912422 bytes.
2017-07-12 16:01:46,158 INFO - Iter 1280, Minibatch Loss= 39855.289062, Training Accuracy= 0.17969
2017-07-12 16:01:46,159 INFO - Iter 2560, Minibatch Loss= 14964.132812, Training Accuracy= 0.42969
...
##############################################################################
...
```

The output of your code is printed in the `Run Output` section of the logs, in between the printed `#########` lines. Anything you log or print in your code will appear here. Using the `-t` (tail) flag streams the logs as they are generated.

You can also view the logs in your browser using your `Job URL`. *Note:* Unlike the `-t` flag in the CLI, the logs displayed in the browser are currently *not* refreshed dynamically. Please refresh your browser periodically or press `F5`.

### Viewing the output

The model that we trained does not save any models. We will explore how to save models in the following tutorial.

### Iterating on your project

You can edit your code locally and run new jobs using the [floyd run](../commands/run.md) command. The CLI will upload the new version of your code and submit another job. FloydHub manages and keeps track of all the jobs you run in your project. 

To view all the jobs in your current project, you can either use the `floyd status` command from your CLI, or you can visit the `Project URL` in your browser.

Example: `www.floydhub.com/alice/quick-start`

![Project view](../img/project_view.jpg)


{!contributing.md!}
