Terminate a queued or running job.

### Usage
```bash
floyd stop ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job. You can get the ID by running the [status](#status) command.    |

### Description
Sometimes you want to terminate a job before it can finish. The stop command sends a request 
to the server to stop the job. You can view the [status](#status) of the job to confirm. When you stop 
a job, you will be charged only for the duration your job was running.

### Example
```bash
$ floyd stop FAGrKvd6GqwVdHMxxMwBZG
Experiment shutdown request submitted. Check status to confirm shutdown
```
---------------------------------
## floyd logout

### Description
Logout the CLI from Floyd 

### Usage
```bash
floyd logout
```
