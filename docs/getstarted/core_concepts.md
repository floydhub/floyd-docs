# Core Concepts

FloydHub is a platform that enables a workflow that data scientists use to
create deep learning models more efficiently. FloyHub allows data scientists to
work more effectively by relieving them of the hassle of maintaining and
provisioning deep-learning servers, allowing them to focus on the science. It's
deep learning without the DevOps.

The topics essential to understanding and effectively using FloydHub and its
workflow can be broken down into the following categories:

- [Projects](#projects)
- [Jobs](#jobs)
- [Datasets](#datasets)
- [Environments](#environments)
- [Output](#output)

## Projects
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

In short, think of a project as a group of [jobs]() aimed at accomplishing the
same goal.

## Jobs
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
FloydHub and run on one of FloyHub's powerful deep-learning servers. Because
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
a job, your code will be sent to a powerful deep-learning server that has your
datasets mounted to it and run there.

You can specify the places where your datasets will be
[mounted](../guides/data/mounting_data) on the server, but you'll have to take
care that your code references your datasets using the file paths where the
data will be on the *server*, not where you have them locally. You'll need to
make sure that your code references your data in the
right place (the place where the data is mounted on the deep-learning server).

### Key Concepts
The main things you need to understand about datasets on FloydHub are:

1. [How to upload a dataset](../guides/create_and_upload_dataset)
2. [How to attach, or "mount", a dataset to a job](../guides/data/mounting_data) so your code can use it

Equally important to knowing how to do those things is making sure that your
code knows where to find your dataset during a job.

## Environments
Locally, you've probably got a few different versions of Python and/or your
preferred deep learning libraries installed, etc. FloydHub has a myriad of
different deep learning environments to choose from, which already have these
dependencies installed, and have varying levels of hardware to meet your needs.
When you run a job on FloydHub, you'll be able to specify the environment you
want use, straight from the command line.

If FloydHub's stock deep learning environments don't meet your needs, you can
create a custom environment for your job. See [this
guide](../guides/jobs/installing_dependencies) for instructions on that.

The main things you need to understand about environments on FloydHub are how
to specify which of the available environments you want to use for your job,
and how to customize your environment if the available environments don't meet
your needs.

## Output
Output is anything from a job that you want to save for future use. The most
common form of output are model checkpoints (the weights and biases of your
model) that you developed during a job. You can save these checkpoints (or
anything else you'd like to preserve) during a job, and have them to reference,
download, and reuse in the future.

Output is the way that you can link jobs together. You run a job to test an
idea you have. If it works, you may want to start where you left off and run
another job. If going down that path leads to a dead end, you may want to go
back to a previous output and start again from there. Knowing how to store
output is key to optimizing your deep learning workflow.

Saving and reusing output on FloydHub tends to feel foriegn to a lot of people
who are new to FloydHub and are used to working on their own machines, but once
you learn how to do it, it becomes very simple and is one of the most valuable
parts of the FloydHub workflow.

### Key concepts
The main things you need to understand about output on FloydHub are:

1. [How to capture/save output from a job](../guides/data/storing_output)
2. [How to use it again in a future job](../guides/reusing_output)

Understanding these concepts will allow you to successfully iterate on ideas
and will make your workflow much more efficient.

