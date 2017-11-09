You can link jobs by mounting the output of one job as the input of a new job.
This allows you to iterate on the ouput of a past job. Output is mounted to a
job in the same way data is. To learn more about mounting data, see [this
guide](data/storing_output).

You can refer to the output of a job by its name with `/output` appended to it.
For example: `floydhub/projects/handwriting-recognition/12/output` refers to
the output of the job `floydhub/projects/handwriting-recognition/12`

Use the `--data` flag in the `floyd run` command, mount past output to a job,
just as you would to mount a dataset. For example:

```
$ floyd run \
  --data floydhub/projects/handwriting-recognition/12/output:/filtered_training_data \
  "python train.py"
```

This will make the output of `floydhub/projects/handwriting-recognition/12`
available at `/filtered_training_data` for the new job to use.

Note: You need to have access to a job to be able to mount its output.
