View the output of a job.

### Usage
```bash
floyd output [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL. The output directory can be viewed in the browser. |
| NAME or ID |      | Name or ID of your job. |

### Description
Most jobs generate output. Any output that needs to be retained after the job is finished should be send to `/output` path.
This is the only path Floyd will preserve. The output command gives the url to access this output. This command by default opens the 
output url in your default browser.

### Example
```bash
$ floyd output floydhub/projects/style-transfer/4
Opening output directory in your browser ...
```

### Downloading output

To download the output you can use the data [clone](data.md#floyd-data-clone) command.

{!contributing.md!}
