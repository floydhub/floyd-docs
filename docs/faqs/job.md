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
[download files](../guides/download_dataset) from a remote URL
directly into Floyd servers.


### I ran my project in Jupyter mode but the url does not seem to work.

Jupyter notebook server takes a couple of minutes to start. Until then you will get a "Bad Gateway"
or similar error when you access the URL. You can check the status of the Jupyter notebook
by running the [logs](../commands/logs) command.


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
project. If you want to use this output in your next run view [this guide](../guides/managing_output).


### Do I have to pay for the entire time my Jupyter Notebook is running?

Unfortunately, yes. As much as we would like to, we are unable to charge you only for the *computation time*.

This is an engineering challenge. When you start a Jupyter Notebook instance and start executing commands,
your state is maintained in memory (both CPU and GPU memory). So the instance has to be alive for the
entire duration of your notebook, not just when you are executing commands.

For example, when you execute `import tensorflow`
command, Tensorflow will allocate the entire GPU memory to the current session and waits for the next command. This makes the instance unusable by anyone else, so we have to charge you for the duration your Notebook is alive.


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



{!contributing.md!}
