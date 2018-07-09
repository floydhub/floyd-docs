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
| `--mode [jupyter|serve]` |  command  | Specify the mode you want to run the project. The default behavior executes the command you specify. See [jupyter](../guides/jupyter) and [serve](#serve) sections for more info on them. |
| `--no-open` |    | You can disable the CLI from opening the jupyter notebook url. It will print the URL instead. |
| `--env [tensorflow|tensorflow:py2|...]` |  tensorflow  | Specify the environment you want to use for your project. See [environments](../guides/environments) for the full list. |
| `--message <message_str>` |    | Attach a message to the specific run of the project. |
| `--tensorboard` |    | Starts tensorboard in the environment. Tensorboard URL can be found in the dashboard. |
| `--max-runtime <time_in_seconds>` |    | Maximum runtime duration allowed for this job. FloydHub will terminate if job is running after this duration. |
| `-f`, `--follow` |    | Stream the logs (alias for -t/--tail) |
| command |    | Command to execute when running your project on Floyd. |

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
$ floyd run "python train_tf.py -lr 0.01 -output /output/model.bin"
```
### Jupyter notebook
Floyd supports running Jupyter/iPython notebooks on the server. Make sure that the notebook (.ipynb) files are present in the
current directory. Use `--mode jupyter` and you will be presented with a URL to view your Jupyter environment. You do not need
to specify a command in this mode. See [jupyter](../guides/jupyter) page for more details.

#### Example
```bash
$ floyd run --mode jupyter
...
Path to jupyter notebook: https://www.floydhub.com/notebooks/g8uGRZFQz85meArJGToEcs
```

### Maximum Runtime (in seconds)

The `--max-runtime` flag lets you set a maximum runtime duration for your job. If a running job 
exceeds its maximum runtime, FloydHub will stop the job and save any output that was 
generated until that point.

#### Example
```bash
$ floyd run --mode jupyter --max-runtime 3600
...
Path to jupyter notebook: https://www.floydhub.com/notebooks/g8uGRZFQz85meArJGToEcs
```
This notebook job will automatically be terminated after 1 hour.

### Attaching multiple datasets

You can attach upto 5 datasets when you run a project using the run command. You can specify both
datasets you uploaded and output datasets of your previous runs. You can specify the mount point
also when you specify the data id to mount.

#### Example:
```bash
$ floyd run --data udacity/datasets/celeba/1:training --data udacity/datasets/mnist/1:testing "python script.py"
```
The above datasets will be mounted at `/training` and `/testing` respectively.

### Serve
Floyd can be used to host the model you generated as a REST api. This api can be used to evaluate your model over HTTP.
Use `--mode serve` and you will be presented with a URL to access your API. Floyd currently supports only Flask apps.
It runs app.py file and expects the service to run on port 5000. You do not need to specify a command in this mode.
See [serve](../examples/style_transfer/#serve-mode) page for more details.

#### Example
```bash
$ floyd run --mode serve
...
URL to service endpoint: https://www.floydlabs.com/expose/mkxjJa46aJBdwP4AEdKxfU
```

{!contributing.md!}
