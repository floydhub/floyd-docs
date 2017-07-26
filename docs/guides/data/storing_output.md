## Storing output data

Most jobs generate output files (eg. model checkpoints, logs, evaluation output). In Floyd, `/output` is a special directory used to store outputs. 

Any file or directory you create at runtime under the `/output` directory will be retained and available to you for download after your job finishes.

#### Example 

This job runs a Python script called `helloworld.py` and pipes its output into the file `/output/my-output-file.txt`:

```bash
$ floyd init quick-start
$ floyd run "python helloworld.py > /output/my-output-file.txt"
Syncing code ...
...
```

Since the file is created under the special `/output` directory, it will be saved. You can view or refer to this output using the [floyd output](../../commands/output) command

```bash
$ floyd output floydhub/projects/quick-start/1/output
Opening output directory in your browser...
```

Alternatively, you can visit the `Output` tab of the job on your dashboard

![Job Output View](../../img/job_output_view.jpg)

## Using output as a data source

You can use the output of one job as the input to your next job. To see how to mount output data, please see [this guide](./mounting_data#mounting-the-output-of-another-job)

{!contributing.md!}
