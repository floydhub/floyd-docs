You can link jobs by mounting the output of one job as the input of a new job.
This allows you to iterate on the ouput of a past job. Output is mounted to a
job in the same way data is. To learn more about mounting data, see [this
guide](data/storing_output).

You can refer to the output of a job by its name.
For example: `mckay/projects/quick-start/1/` refers to
the output of the job `mckay/projects/quick-start/1`

Use the `--data` flag in the `floyd run` command, mount past output to a job,
just as you would to mount a dataset. For example:

```
$ floyd run \
  --data mckay/projects/quick-start/1/:model "python train.py"
```

This will make the output of `mckay/projects/quick-start/12`
available at `/floyd/input/model` for the new job to use.

Note: You need to have access to a job to be able to mount its output.
