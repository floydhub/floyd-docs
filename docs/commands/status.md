View status of your jobs.

### Usage
```bash
floyd status [NAME or ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| Name or ID |      | ID of your job. |

### Description
Shows the status of a run, if the name is specified. It can also list the status of all
the runs in the current project. You need to be in the project directory for this command to work.

This command can take a [shortened job name](../guides/shortnames).

### Examples
```bash
$ floyd status
JOB NAME                                 CREATED       STATUS      DURATION(s)  INSTANCE    DESCRIPTION
---------------------------------        ------------  --------  -------------  ----------  -------------
floydhub/projects/mnist-tensorboard/3    19 hours ago  success              16  g1
floydhub/projects/mnist-tensorboard/2    19 hours ago  success               3  c1
floydhub/projects/mnist-tensorboard/1    5 days ago    success              26  c1
```

{!contributing.md!}
