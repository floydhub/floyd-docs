### Why does `floyd status` return an empty list even though I have several
runs in my account?

Floyd CLI uses the project directory to store the run information (similar to git). So you need
to be in the directory where you initialized the project and you should be able to see all your
runs. You can also use the [web dashboard](https://www.floydhub.com/projects) to view all your
projects in one place.


### What do I do when I get "What do you do when you get “You are over the allowed limits for this operation. Consider upgrading your account”?

Floydhub currently allows only 1 active job per user for trial plan and 3 active jobs for individual plan. If you require more concurrency, contact
us from the [pricing](https://www.floydhub.com/pricing) page.


### I get "Too many open files" error when I run my project.

Floyd CLI throws this error when you have too many files in your current directory that needs to be uploaded.
The actual limit depends on your OS / machine specs.

You can either:

1. Remove unnecessary files from the directory (like build directory, docs etc.)
2. Add them to `.floydignore` file. Floyd CLI will just ignore these directories.
See the [floydignore](../guides/floyd_ignore) documentation to understand how this can be configured.
3. Tar them into a single file and untar them at runtime.

Alternatively, instead of uploading files from your local machine, you can also
[download files](../guides/create_and_upload_dataset/#download-large-datasets-directly-to-floydhub-from-the-internet) from a remote URL
directly into Floyd servers.


### Why do I get an "Experiments limit reached" error when I run a job?

FloydHub currently allows only 1 active job in the free Trial plan and 3 active jobs in the Individual plan.
If you see an `Error: Experiments limit reached` message when you run a job, it means you have maxed out your
concurrency limits. Please stop you running job(s) or wait for them to finish, and try again.

We have to enforce this concurrency constraint because we have a finite number of GPU machines and have to ensure that no single user is starving the group. In the near future, we will support queueing of jobs so that you can queue multiple jobs to be run as slots become available.


### Am I using the GPU instance by default?

Jobs are run on CPU instances by default. You can specify `--gpu` to run them on GPU instances.


### My job is taking a while to "sync changes". How do I make it go faster?

Floyd CLI uploads *all* the files in your current directory before starting your experiment.
There are a few ways to make this go faster:

1. Remove unnecessary files from the directory (like build directory, docs etc.)
2. Add sub-directories to `.floydignore` file. Floyd CLI will ignore and not upload these sub-directories.
See the [init](../commands/init#description) command and [ignore files guide](../guides/floyd_ignore) to understand how this can be configured.
3. If you have large data files consider uploading them separately as a [data source](../commands/data).
You can then [refer](../guides/mounting_data) to them in your project.


### My job finished but how I do I see my output?

You can use the floyd [output](../commands/output) command to view the output of your
project. If you want to use this output in your next run view [this guide](../guides/data/mounting_data#mounting-the-output-of-another-job).


### Why is my job in the "Queued" state for several minutes?

This means that a machine is being prepared to run your job.

Most times, we have several CPU and GPU machines that are ready and your job can start execution in a few seconds. During high traffic periods, we may not have a machine ready for you and have to spin up a new instance for your job on-demand (details below). This might take up to 10 minutes in some cases. We are actively working on reducing this wait time.

**Details**: When you execute a `floyd run` command, Floyd does several things in the background:

- Provision a CPU or GPU instance on the cloud
- Set up a deep learning environment with GPU drivers and the correct environment (as specified by `--env`) installed using Docker
- Mount any data you specify using the `--data` flag

Each of these steps can take up to a couple of minutes. Usually Steps 1 and 2 are already done, but during peak usage hours, we might have to do this on-demand.


### Why are my logs not displayed in real-time?

You can stream your logs from the CLI using the `floyd logs -t <JOB_NAME>` command. However, sometimes you may notice that the logs are not displayed in real-time. This is because of output buffering. Please make sure that your logs are flushed out if you prefer to view real-time logs.

For example, in Python:

```python
import sys
...
print("Hello world")
sys.stdout.flush()
```

### Why did my job timeout after 1 hour?

You are likely in the Free Trial Plan. Jobs run in the trial plan have a maximum runtime of 1 hour. It will automatically timeout after that.

![1HourTimeout](../img/1HrTimeout.jpg)

You can upgrade to the [Paid Plan](https://www.floydhub.com/pricing) to overcome these limits.


### Why was my CPU job Killed without warning?

Occasionally, you may notice that your CPU job died without warning. The output logs just display `Killed`. For example,

```bash
################################################################################

2017-07-24 03:33:42,530 INFO - Run Output:
...
2017-07-24 03:33:52,920 INFO - Using TensorFlow backend.
2017-07-24 03:34:04,381 INFO - >> loading UNet of size 1152x256...
2017-07-24 03:34:10,942 INFO - Epoch 1/100
2017-07-24 03:35:17,221 INFO - Killed
2017-07-24 03:35:18,680 INFO -
################################################################################
```

This happens when your machine runs out of memory (OOM). i.e. your job consumes more memory than is available on our CPU machines.

All jobs run on FloydHub are executed inside a Docker container. Our current CPU machines have [7GB memory](https://www.floydhub.com/pricing). When memory used by your job exceeds 7GB, Docker automatically kills the job to protect the system and avoid abuse.

The resolution is to optimize your code to consume less memory. For example, read less data into your in-memory datastructures or reduce your batch size. We will be introducing more powerful CPUs, which higher memory in the near future.
