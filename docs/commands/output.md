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
Most jobs generate output. Any output that needs to be retained after the job is finished should be saved inside working directory (`/floyd/home`).
This is the only path Floyd will preserve across all jobs. The output command gives the url to access this output. This command by default opens the
output url in your default browser.

This command can take a [shortened job name](../guides/shortnames).

### Example
```bash
$ floyd output alice/projects/download-output/1
Opening output directory in your browser ...
```

### Downloading output

To download the output you can use the data [clone](data.md#floyd-data-clone) command.

{!contributing.md!}
