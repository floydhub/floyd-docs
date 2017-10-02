Restat/rerun a previous job

### Usage
```bash
floyd restart JOB_NAME [OPTIONS] [COMMAND]
```

### Options
| Name, shorthand | Description             |
| --------------- | ----------------------- |
| JOB_NAME        | Name or ID of your job. |
| All the `[OPTIONS]` and `[COMMAND]` of `floyd run` as documented [here](run)|

### Description

Use this command to restart/rerun a previous job.  Any `[OPTIONS]` or
`[COMMAND]` passed to `floyd restart` will override the `[OPTIONS]` or
`[COMMAND]` of the original job. This can be useful if you want to run a
previous job with different `[OPTIONS]` (like a different instance type), or
override its `[COMMAND]`.

When using `floyd restart`, a copy of your code is not uploaded (since the code
of the previous job is used). This can save on startup time.

### Examples

```
# Override the command
$ floyd restart mckay/projects/mnist/1 "python train.py"
```

```
# Run the job on a GPU server
$ floyd restart mckay/projects/mnist/1 --gpu
```

```
# Run the job on a GPU server
$ floyd restart mckay/projects/mnist/1 --gpu
```

{!contributing.md!}
