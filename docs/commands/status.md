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
Shows the status of a run, if the ID is specified. It can also list the status of all 
the runs in the current project. You need to be in the project directory for this command to work.

### Example
```bash
JOB NAME                           CREATED       STATUS      DURATION(s)  INSTANCE    DESCRIPTION
---------------------------------  ------------  --------  -------------  ----------  -------------
floydhub/projects/quick-start/131  19 hours ago  success              16  g1
floydhub/projects/quick-start/130  19 hours ago  success               3  c1
floydhub/projects/quick-start/129  5 days ago    success              26  c1
```

{!contributing.md!}
