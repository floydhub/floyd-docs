Delete a job.

### Usage
```bash
floyd delete [ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job. |
| `--yes`, `-y` | False  | Skip delete confirmation step |

### Description
Deletes a job from FloydHub. The experiment information is no longer 
available. You will not be able to access the code uploaded to run the 
experiment.

Note: You do *not* have to be in the project directory to run this command.

### Example
```bash
$ floyd delete J2ggstKWTNmL24nQTgi36o
Delete Run: floydhub/fastText:1? [y/N]: y
Experiment deleted
```
