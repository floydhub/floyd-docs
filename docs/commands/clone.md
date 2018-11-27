Clone the code for a specific job.

### Usage
```bash
floyd clone [OPTIONS] JOB_NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| JOB_NAME or ID |      | Name or ID of your job. |
| `--path <dir_path>`, `-p <dir_path>` |      | Download files in a specific path from job. |

### Description
Use this command to clone an existing project on floyd. The code used for the job is downloaded to the
current directory. This will override any existing file or directory in the process.

This command is a great way to get started on floyd by starting from an existing project.

This command can take a [shortened job name](../guides/shortnames).

### Example

Example1: Download the full Job.
```bash
$ floyd clone floydhub/projects/deep-photo-styletransfer/4
Downloading the tar file to the current directory ...
Untarring the contents of the file ...
Cleaning up the tar file ...
```

Example2: Download the content of the `models` directory from the `deep-photo-styletransfer/4` job.
```bash
$ floyd clone -p models floydhub/projects/deep-photo-styletransfer/4
Downloading the tar file to the current directory ...
Untarring the contents of the file ...
Cleaning up the tar file ...
```

{!contributing.md!}
