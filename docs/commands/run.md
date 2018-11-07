Run your project on Floyd.

### Usage
```bash
floyd run [OPTIONS] [COMMAND]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--gpu/--gpu2/--cpu/--cpu2` |  cpu  | If specified, runs the job on a GPU (K80) / GPU2 (V100) instance or CPU (2 cores) / CPU2 (8 cores) instance. See instance specifications on the [pricing](https://www.floydhub.com/pricing) page. |
| `--data <ID:mount>` |    | `ID` of the data source to link to. `mount` specifies the path to mount it at. You can use this parameter multiple times. See [data](../guides/data/mounting_data) section for more details. |
| `--mode [job|serve]` |  job  | Specify the mode you want to run the project. The default behavior executes the command you specify. See [serve](#serve) section for more info. |
| `--env [tensorflow|tensorflow:py2|...]` |  tensorflow  | Specify the environment you want to use for your project. See [environments](../guides/environments) for the full list. |
| `--message <message_str>` |    | Attach a message to the specific run of the project. |
| `--max-runtime <time_in_seconds>` |    | Maximum runtime duration allowed for this job. FloydHub will terminate if job is running after this duration. |
| `-f`, `--follow` |    | Stream the logs (alias for -t/--tail) |
| command |    | Command to execute when running your project on Floyd. |
| command |      | Command to execute when running your project on Floyd. |

!!! warning "Encoding issue!"
    _This is a common issue for **Windows users**_: This occurs when your Windows terminal is using a different encoding from the one expected by the remote machine. Here are some examples:
    
    1. Slash and single quote issue: `floyd run \ --data alice/datasets/test \  'python test_Sony.py'` is translated as `floyd run --data alice/datasets/test '\ \ \ \ '"'"'python test_Sony.py'"'"''`  
    2. Double quotes issue: `floyd run "python test_Sony.py"` is translated as `floyd run  ''"'"'python test_Sony.py'"'"''`

    Unfortunately, there isn't a silver bullet to identifying this issue, but you can use the `Command` view of the Job's Overview page to help debug and identify this issue. More generally, if you notice this issue, you can try to switch single quotes with double or vice versa, and remove the slash if you are indenting the commands on multiple lines - these changes usually fix the issue in 99% of the cases. If not, please reach out to us at support@floydhub.com.


### Description
This command syncs the code tracked by the CLI to the Floyd servers and executes your command. You can see the progress
with [status](./status) command. To view the logs from your code use [logs](./logs) command.

### Example
```bash
$ floyd run --env tensorflow --gpu "python mnist_cnn.py"
Syncing code ...
NAME
-----------------------------
floydhub/projects/lung-cancer/2

...
$ floyd logs floydhub/projects/lung-cancer/2
```

### floyd_requirements.txt
Floyd runs standard Docker images for various deep learning frameworks.(See [environments](../guides/environments) for details). If your
code requires additional Python dependencies you can specify them in a `floyd_requirements.txt` file and place it at the root
directory of your project. These dependencies will be installed before running your code.

#### Example
```bash
$ cat floyd_requirements.txt
Pillow
scipy
$ floyd run "python train_tf.py -lr 0.01 -output models/model.bin"
```

### Maximum Runtime (in seconds)

The `--max-runtime` flag lets you set a maximum runtime duration for your job. If a running job
exceeds its maximum runtime, FloydHub will stop the job and save any output that was
generated until that point.

#### Example
```bash
$ floyd run --max-runtime 3600
```
This job will automatically be terminated after 1 hour.

### Follow

The `--follow` flag allows you to immediately display the Logs of the running Job without launching the `floyd logs` command.

```bash
$ floyd run --env tensorflow --gpu --follow "python mnist_cnn.py"
Creating project run. Total upload size: 1.1MB
Syncing code ...
[================================] 1300/1300 - 00:00:00
Opening logs ...
Waiting for logs ...

2018-07-09 07:03:23,744 INFO - Preparing to run TaskInstance ...

#################################################

2018-07-09 07:03:25,596 INFO - Run Output:
...

#################################################

2018-07-09 07:03:40,202 INFO - Waiting for container to complete...
2018-07-09 07:03:40,358 INFO - Persisting outputs...
2018-07-09 07:03:42,181 INFO - Creating data module for output...
2018-07-09 07:03:42,212 INFO - Data module created for output.
2018-07-09 07:03:42,212 INFO - Persisting data in home...
2018-07-09 07:03:42,333 INFO - Home data persisted.
```

### Attaching multiple datasets

You can attach up to 5 datasets when you run a job using the run command. You can specify both
datasets you uploaded and output datasets of your previous runs. You can specify the mount point
also when you specify the data id to mount.

#### Example:
```bash
$ floyd run --data udacity/datasets/celeba/1:training --data udacity/datasets/mnist/1:testing "python script.py"
```
The above datasets will be mounted at `/training` and `/testing` respectively.

### Serve
FloydHub can be used to host the model you generated as REST API. API can be used to evaluate your model over HTTP protocol.

Use `--mode serve` and you will be presented with a URL to access your API. You do not need to specify a command in this mode.
See [serving document](../guides/serving/) for more details.

#### Example
```bash
$ floyd run --mode serve
...
URL to service endpoint: https://www.floydlabs.com/serve/mkxjJa46aJBdwP4AEdKxfU
```

{!contributing.md!}
