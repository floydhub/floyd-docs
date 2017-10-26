!!! important "Quick Look"

    ## Jupyter Notebook Jobs in Web Dashboard:

    ![restart job image](../../img/restart_jupyter.jpg)

    ## Using Floyd CLI:

    ```
    $ floyd restart mckay/projects/mnist/1 --gpu "python train.py"
    ```

## Jupyter Notebook Job in Web Dashboard:

Jupyter Notebook jobs can be restarted through the web dashboard. Navigate to
the job's detail page, and click the `Restart` button in the top right corner
as shown in the screenshot below:

![restart job image](../../img/restart_jupyter.jpg)

This will start your Jupyter Notebook where you last left it. If you'd like to
restart your job back where it *started*, just restart the previous job. See the 
restart workflow in action:

![restart job image](../../img/restart_jupyter.gif)

Jupyter Notebook jobs can also be restarted using Floyd CLI, as detailed below.

## Using Floyd CLI:

All jobs can be restarted/re-run using Floyd CLI's `floyd restart` command. This
command takes a `<job_name>`, and allows the same `[OPTIONS]` and `[COMMAND]`
parameters as the `floyd run` command.

This is most useful when you want to restart/re-run a job, but override certain
parameters of the job (like upgrading its instance type) or overriding the
`[COMMAND]` that was used in the job.

Below are a few examples. Each examples restarts/re-runs the
`mckay/projects/mnist/1` job, but overrides different parts of the job:

```
# Override the command
$ floyd restart mckay/projects/mnist/1 "python train.py"
```

```
# Run the job on a GPU server
$ floyd restart mckay/projects/mnist/1 --gpu
```

```
# Run the job with a new version of a dataset
$ floyd restart mckay/projects/mnist/1 --data mckay/datasets/mnist/2:mnist
```

## Parameter sweeping:

A great use case for the restart command is when you need to run a series of jobs with 
different training parameters. You just need to make your training script take in all the 
parameters from the command line. After you run the first job using the `floyd run` command:

```
# Run the first job with initial parameters
$ floyd run --gpu "python train.py --learning-rate 0.01 --batch-size 8 --epochs 100"
...
JOB NAME
--------------------------------
mckay/projects/tf-grid-search/1
```

Now you can just restart this job with different set of parameters:

```
# Change the learning rate
$ floyd restart mckay/projects/tf-grid-search/1 --gpu "python train.py --learning-rate 0.05 --batch-size 8 --epochs 100"
```

```
# Change the number of epochs
$ floyd restart mckay/projects/tf-grid-search/1 --gpu "python train.py --learning-rate 0.05 --batch-size 8 --epochs 500"
```

This gives you the ability to try a range of parameters without uploading your code each time.
