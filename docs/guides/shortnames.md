When a Floyd CLI command takes a job name, a dataset name, or a job output, you can always specify a full length name, like this:

Job:
```
$ floyd status mckay/projects/quick-start/1
```

Dataset:
```
$ floyd data status mckay/datasets/mnist/1
```

Job Output:
```
$ floyd status mckay/projects/quick-start/1/output
```

Floyd CLI allows you to use shortened names instead of full-length ones. When
you leave out parts of a name, the CLI does the following:

1. When a username is missing, the username of the logged-in user is used.
2. When a project or dataset name is missing, the name of the currently
    initialized project or dataset is used.
3. When a job number or a dataset version number is missing, the most recent version is used.
4. If you leave out the `/projects/` or `/datasets/` part of the name, it is
    inferred based on the command and other parts of the name. In most cases,
    you shouldn't have to specify these parts of the name. However, if you want
    to specify an output, you'll need to make sure your name has `/output` at the
    end of it, output names are otherwise the same as job names.

These assumptions allow you to avoid typing out a full name in almost any
situation.

## Examples

Below are some examples on how to use shortened names for jobs, datasets, and
outout. While only a selection of Floyd CLI commands are used in these
examples, anywhere job, output, or dataset name is used, a shortened name can
be used.

Below is a list of commands that take shortened names. Click on any item in the
list to go to its documentation:

- [`floyd status <job_name>`](../commands/status)
- [`floyd clone <job_name>`](../commands/clone)
- [`floyd info <job_name>`](../commands/info)
- [`floyd logs <job_name>`](../commands/logs)
- [`floyd output <job_name>`](../commands/output)
- [`floyd stop <job_name>`](../commands/stop)
- [`floyd delete <job_name>`](../commands/delete)
- [`floyd restart <job_name>`](../commands/restart)
- [`floyd run --data <dataset_or_output_name>:<mount_point>`](../guides/data/mounting_data)
- [`floyd data status <dataset_name>`](../commands/data)
- [`floyd data clone <dataset_or_output_name>`](../commands/data)
- [`floyd data output <dataset_or_output_name>`](../commands/data)
- [`floyd data delete <dataset_name>`](../commands/data)

## Job Name Examples

Here are some examples that demonstrate how to use shorter names when
referencing a job. For these examples, we'll assume your username is `fooster`,
the project you've initialized in the current directory is called `my_project`,
and the last job you ran in `my_project` is number `3`. Each example will show
two code snippets: the first showing a command using a shortened name, and a
second showing the full-length equivalent of the first command.

Below, we leave the job name completely blank and fall back on all our defaults: current user's username, current project's name, and most recent job number:

```
$ floyd logs
```
```
$ floyd logs fooster/projects/my_project/3
```

Here, we want to specify a job number of a past job, but still under our current project:

```
$ floyd logs 1
```
```
$ floyd logs fooster/projects/my_project/1
```

Here, we want to specify a job under a different project, but still a project
owned by our user. Because we don't specify a job number, the latest job will
be used (let's say it's 5):

```
$ floyd logs other_project
```
```
$ floyd logs fooster/projects/other_project/5
```

What if we want to specify job 3 of `other_project`? Like this:

```
$ floyd logs other_project/3
```
```
$ floyd logs fooster/projects/other_project/3
```

Here, we specify a different users's project. Let's say it's a user named
`alice` and the project is called `quick-start`. Because we don't want the most
recent job, we'll specify the job number:


```
$ floyd logs alice/quick-start/1
```
```
$ floyd logs alice/projects/quick-start/1
```

## Dataset Name Examples


Here are some examples that demonstrate how to use shorter names when
referencing a dataset. For these examples, we'll assume your username is `fooster`,
the dataset you've initialized in the current directory is called `my_dataset`,
and the most recent version of the dataset is `2`. Each example will show
two code snippets: the first showing a command using a shortened name, and a
second showing the same command with the full-length equivalent of the
shortened name.

Here, we check the status of an older dataset version (version 1):

```
$ floyd data status 1
```
```
$ floyd data status fooster/datasets/my_dataset/1
```

Here, we open the browser to view the most recent version of our dataset.
Specifying nothing uses all our defaults--the current user's username, the
dataset initialized in the current directory, and the most recent version of
the dataset:

```
$ floyd data output
```
```
$ floyd data output fooster/datasets/my_dataset/1
```

In this example, let's assume we're in a directory with a project initialized
in it (otherwise the `floyd run` command would not work). We'll mount a dataset
called `hello` that belongs to the current user. We want the most recent
version of the dataset (which we'll say is `2`), so we don't specify the
version number.

```
$ floyd run --data my_dataset:model 'python train.py'
```
```
$ floyd run --data fooster/datasets/hello/2:model 'python train.py'
```

## Output Name Examples

When referring to the output of a job, you'll need to be sure to tack `/output`
onto the end of the shortened name so the CLI knows you're referring to the
job's output, and not the job itself. In the examples below, We'll assume that
our username is `fooster` and that we have a project named `my_project`
initialized in the current directory. Here are a couple examples:

Below, we want to mount the output of `fooster/projects/my_project/3/output` at `/model`:

```
$ floyd run --data 3/output:model 'python eval.py'
```
```
$ floyd run --data fooster/projects/my_project/3/output:model 'python eval.py'
```

Here we clone the output of job number 1 of our current project:

```
$ floyd data clone 1/output
```
```
$ floyd data clone fooster/projects/my_project/1/output
```
