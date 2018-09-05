!!! important "Quick Look"
    On the job screen on floydhub.com:

    ![Download Output](../img/browsing_output/files.png)

    Or from the CLI:
    ```
    $ floyd output <username>/projects/<project_name>/<run_number>
    ```

After you've [saved output](data/storing_output) from a job, you can browse the
output of the job on `floydhub.com`.

To learn how to re-use output in a new job, see [this
documentation](reusing_output).

## From floydhub.com
From the job's page on floydhub.com, you can browse and download the output of
the job by using the "Browse" and "Download" icons found on the "Files" tab:

![Download Output](../img/browsing_output/viewer.png)

## From the CLI
To open the browsing window from the CLI, use the
[`floyd output`](../commands/output) command and pass it the path of the job:

```bash
$ floyd output alice/projects/download-output/1
Opening output directory in your browser ...
```