View the logs of your run

### Usage
```bash
floyd logs [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL. The logs can be viewed in the browser. |
| `--tail`, `-t` |      | Stream the output of your code in real-time. |
| NAME or ID |      | Name or ID of your job. |

### Description
Any data sent to STDOUT and STDERR by your code will become available here. Make sure your
logs are flushed out if you prefer to view logs in real-time. There will be some information from
Floyd servers before and after your project logs. They are usually useful for debugging purposes.

This command can take a [shortened job name](../guides/shortnames).

### Example
```bash
$ floyd logs floydhub/projects/deep-photo-styletransfer/4
Preparing to run
Starting container...

#################################################

Run Output:
...

#################################################

Waiting for container to complete...
[success] Finishing execution
```

{!contributing.md!}
