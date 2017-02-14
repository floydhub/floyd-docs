View status of your jobs.

### Usage
```bash
floyd status [ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job. |

### Description
Shows the status of a run, if the ID is specified. It can also list the status of all 
the runs in the current project. You need to be in the project directory for this command to work.

### Example
```bash
$ floyd status
RUN ID                  CREATED         STATUS      DURATION(s)  NAME                           INSTANCE      VERSION
----------------------  --------------  --------  -------------  -----------------------------  ----------  ---------
dTe2cJJrNR2CBD74rSZXPA  31 minutes ago  success             108  floydhub/tensorflow-project:7  cpu                 2
B8wkLbuGs2mtjhe9jqrkYT  2 hours ago     success            2349  floydhub/tensorflow-project:7  gpu                 1
```
