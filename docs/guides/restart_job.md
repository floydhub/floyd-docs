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
restart your job back where it *started*, just restart the previous job.

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
