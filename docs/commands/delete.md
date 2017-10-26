Delete one or more floyd jobs.

### Usage
```bash
floyd delete [IDS]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| IDS |      | One or more IDs of your job. |
| `--yes`, `-y` | False  | Skip delete confirmation step |

### Description
Deletes a job from FloydHub. The experiment information is no longer 
available. You will not be able to access the code uploaded to run the 
experiment. You need to make sure that the project is currently not 
running. If so, you can use the [stop](stop.md) command for that.

Note: You do *not* have to be in the project directory to run this command.

### Example
```bash
$ floyd delete floydhub/projects/fastText/1 floydhub/projects/cnr/1
Delete Run: floydhub/projects/fastText/1? [y/N]: y
Experiment deleted
Delete Run: floydhub/projects/cnr/1? [y/N]: y
Experiment deleted
```

{!contributing.md!}
