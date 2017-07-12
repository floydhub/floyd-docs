In this guide, we will explain how to attach a dataset to your project run.

### Quick Preparation Checklist

- You must have a [FloydHub account](https://www.floydhub.com/signup)
- You must be [logged in to your web dashboard](https://www.floydhub.com/login)
- You must have `floyd-cli` [installed on your computer](basics/install.md)

You can use the [floyd login](../commands/login.md) command to login to your FloydHub account through your command line

## Mounting datasets

Floyd datasets are directories of data files that can be used in a project run. You can view the datasets you 
have uploaded in the [datasets page](https://www.floydhub.com/datasets) in the dashboard. You can also view 
public datasets by searching for it on FloydHub.

### Data name

To mount a dataset you need to specify its names along with the version. The full name to use here consists of 3 
parts: `<username>/datasets/<dataset_name>/<version>`. 

For example: `floydhub/datasets/mnist/2`.

By default the mount path for the dataset is `/input`. But you can override that by specifying a mount path as 
part of the data name.

For example: `floydhub/datasets/mnist/2:mnist`.

In this case the directory containing the mnist data files.

### Run command

You can specify the name of the data in the [run command](../commands/run.md) using the `--data` flag. For example:

```bash
$ floyd run --data floydhub/datasets/mnist/2:mnist "python train.py"
```

## Mounting output data

In Floyd the output of any project run (that you have access to) can be mounted to a different project run.
You can refer to the output of a project run by its name with `/output` appended to it.

For example: `floydhub/projects/handwriting-recognition/12/output`

This refers to the output of the job: `floydhub/projects/handwriting-recognition/12`

You can mount this using the run command similar to datasets. For example:

```bash
$ floyd run --data floydhub/projects/handwriting-recognition/12:filtered_training_data "python train.py"
```

## Mounting multiple datasets

You can attach upto 5 datasets when you run a project using the run command. This includes both datasets and 
project run outputs. Ensure that the mount points for the datasets are unique.

```bash
$ floyd run --data floydhub/datasets/mnist/2:training --data floydhub/datasets/digits/1:testing "python script.py"
```
In this case the above datasets will be mounted at `/training` and `/testing` respectively.

## Web dashboard

You can view the mounted datasets in a specific job by going to the `data` tab:

![Data Mounts](../img/job_data_view.png)
