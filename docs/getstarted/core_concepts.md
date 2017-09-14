# Core Concepts

The essential points for understanding and effectively using FloydHub can be
grouped into the following categories:

- [Projects](#projects)
- [Jobs](#jobs)
- [Datasets](#datasets)
- [Environments](#environments)
- [Output](#output)

This document serves as an introduction to each of these categories. When
you're ready to dive deeper, each category has its own section in our
documentation that you can explore.

## Projects

!!! tip "Quick Look"
    A project is a group of [jobs]() aimed at accomplishing the same goal. A
    project keeps track of each job, along with its [output](#output) and logs.

!!! warning "Key Points of Understanding"
    - [Creating a project](../guides/basics/create_new)

### Overview

The project is the most central construct of the FloydHub platform.
Understanding what a project is on FloydHub isn't too difficult because it
directly correlates with what you'd think of as a deep learning project outside
of FloydHub: You have a problem you need to solve with a deep learning model.
You get on your computer, create a new directory with a name like `mnist-cnn`
and boom, you've started a new project. In that directory, you'll write some
code, run some experiments, and iterate until you have created a deep learning
model that meets your needs.

On FloydHub, a project is a collection of all the work and iterations you
perform when developing a deep learning model. In contrast to a typical deep
learning workflow, your experiments and iterations (we call them
[jobs](#jobs)) will be versioned and kept organized for you to reference in the
future.

## Jobs

!!! tip "Quick Look"
    A job is an execution of your code on FloydHub's deep-learning servers.

!!! warning "Key Points of Understanding"
    - [Running a job](../commands/run)

### Overview

A job is what pulls together your [code]() and [dataset(s)](), sends them to a
deep-learning server configured with the right [environment](), and
actually kicks off the necessary code to get the data science done.

After a job is completed, you'll be able to go back and reference/review it on
floydhub.com. For each job, you'll be able to see:

1. A snapshot of the code used for the job
2. A record of which [Dataset(s)]() you used for the job
3. A record of what [Environment]() was used for the job
4. The [Output]() and logs of the job

You run jobs using Floyd CLI's `floyd run` command. The command has various
flags and parameters that let you customize how the job runs: What dataset do
you want to use? Where should the dataset be mounted on the server? What
environment do you want to use? Should the server run your job using a CPU or a
GPU? What command(s) should the server use to run your code? Any other commands
you'd like to run on the server to set it up before running your job? Etc.

## Datasets

!!! tip "Quick Look"
    Datasets are securely uploaded to FloydHub. They are versioned and can be
    attached to any job.

!!! warning "Key Points of Understanding"
    - [How to upload a dataset](../guides/create_and_upload_dataset)
    - [How to attach, or "mount", a dataset to a job so your code can use it](../guides/data/mounting_data)
    - [Making sure your code references your data in the correct location](#connecting-code-and-datasets)


### Overview
FloydHub's dataset workflow is one of two things that tend to feel a bit
foreign to users who are used to local development (the other being
[output]()). When working on your local machine, you might have your dataset in
the same directory as your code, or in a directory where you keep many
different datasets. When using FloydHub, datasets are always kept separate from
code.

### Why keep datasets separate from code?
A data scientist tweaks his/her code often during the process of creating a
deep-learning model. However, he/she doesn't change the underlying data nearly
as often, if at all.

Each time you run a job on FloydHub, a copy of your code is uploaded to
FloydHub and run on one of FloydHub's powerful deep-learning servers. Because
your data isn't changing from job to job, it wouldn't make sense to keep your
data with your code and upload it with each job. Instead, we upload a dataset
once, and attach, or "mount", it to each job. This saves a significant amount
of time on each job.

Beyond that, keeping data separate from code allows you to collaborate more
easily with others. A dataset can be used by any user who has access to it, so
teams and communities can work on solving problems together using the same
underlying data.

### Connecting code and datasets
You'll still be writing your code locally when using FloydHub, but when you run
a job, your code will be uploaded to FloydHub and executed on a powerful
deep-learning server that has your datasets mounted to it.

You can specify the places where your datasets will be
[mounted](../guides/data/mounting_data) on the server, but you'll have to make
sure that your code references your datasets with the file paths of the data on
the *server*, not where you might have them locally.

## Environments

!!! tip "Quick Look"
    An environment is what defines the software packages that will be available
    to your code during a job

!!! warning "Key Points of Understanding"
    - [How to select an environment for your job](../guides/data/storing_output)
    - [How to customize your environment](../guides/reusing_output)

### Overview

FloydHub has a bunch of different [deep learning environments to choose
from](../guides/environments). When you run a job on FloydHub, you'll be able
to specify the environment you want use, straight from the command line. You'll
also be able to specify whether you want the job run using a [GPU or a
CPU](../guides/basics/using_gpu).

If FloydHub's stock deep learning environments don't meet your needs, you can
create a custom environment for your job. See [this
guide](../guides/jobs/installing_dependencies) for instructions on that.

## Output

!!! tip "Quick Look"
    Output is any data, logs, or files you want to save for future reference
    and use.

!!! warning "Key Points of Understanding"
    - [How to capture/save output from a job](../guides/data/storing_output)
    - [How to use it again in a future job](../guides/reusing_output)

### Overview

Output is anything from a job that you want to save for future use. The most
common form of output is model checkpoints (the weights and biases of your
model) that you developed during a job. If you save these checkpoints (or
anything else you'd like to preserve) during a job, you'll have them to
reference, download, and reuse in the future.

Output is the way that you can link jobs together: You run a job to test an
idea you have. If it works, you may want to start where you left off and run
another job. If going down that path leads to a dead end, you may want to go
back to a previous output and start again from there. Knowing how to store
output is key to optimizing your deep learning workflow.

[Saving](../guides/data/storing_output) and [reusing](../guides/reusing_output)
output on FloydHub can feel foriegn to users who are used to working on their
own machines. But once you learn how to do it, it becomes very simple and is
one of the most valuable parts of the FloydHub workflow.
