Terminate a queued or running job.

### Usage
```bash
floyd stop NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| NAME or ID |      | Name or ID of your job. |

### Description
Sometimes you want to terminate a job before it can finish. The stop command sends a request
to the server to stop the job. You can view the [status](./status) of the job to confirm. When you stop
a job, you will be charged only for the duration your job was running.

### Example
```bash
$ floyd stop floydhub/projects/mnist-tensorboard/4
Experiment shutdown request submitted. Check status to confirm shutdown
```

{!contributing.md!}
