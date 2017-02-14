View the output of a job.

### Usage
```bash
floyd output [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL. The output directory can be viewed in the browser. |
| ID |      | ID of your job. You can get the ID by running the [status](#status) command.    |

### Description
Most jobs generate output. Any output that needs to be retained after the job is finised should be send to `/output` path.
This is the only path Floyd will preserve. The output command gives the url to access this output. This command by default opens the 
output url in your default browser.

### Example
```bash
$ floyd output dTe2cJJrNR2CBD74rSZXPA
Opening output directory in your browser ...
```
