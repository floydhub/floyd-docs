!!! important "Quick Look"

    ```
    $ floyd restart mckay/projects/mnist/1 --gpu "python train.py"
    ```

All jobs can be restarted/re-run using Floyd CLI's `floyd restart` command. This
command takes a `<job_name>`, and allows the same `[OPTIONS]` and `[COMMAND]`
parameters as the `floyd run` command. You can specify a [shortened job
name](../guides/shortnames) to this command.

This is most useful when you want to restart/re-run a job, but override certain
parameters of the job (like upgrading its instance type) or overriding the
`[COMMAND]` that was used in the job.

Below are a few examples. Each examples restarts/re-runs the
`mckay/projects/quick-start/1` job, but overrides different parts of the job:

```
# Override the command
$ floyd restart mckay/projects/quick-start/1 "python train.py"
```

```
# Run the job on a GPU server
$ floyd restart mckay/projects/quick-start/1 --gpu
```

```
# Run the job with a new version of a dataset
$ floyd restart mckay/projects/quick-start/1 --data mckay/datasets/mnist/1:mnist
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
