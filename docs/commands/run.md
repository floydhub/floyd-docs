Run your project on Floyd.

### Usage
```bash
floyd run [OPTIONS] [COMMAND]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--gpu/--cpu` |  cpu    | If specified, runs the job on a GPU (G1) instance or CPU (C1) instance. See instance specifications on the [pricing](https://www.floydhub.com/pricing) page. |
| `--data <ID:mount>` |    | `ID` of the data source to link to. `mount` specifies the path to mount it at. You can use this parameter multiple times. See [data](../guides/data/mounting_data) section for more details. |
| `--mode [jupyter|serve]` |  command  | Specify the mode you want to run the project. The default behavior executes the command you specify. See [jupyter](../guides/jupyter) and [serve](#serve) sections for more info on them. |
| `--no-open` |   | You can disable the CLI from opening the jupyter notebook url. It will print the URL instead. |
| `--env [tensorflow:py3|tensorflow:py2|...]` | keras:py3  | Specify the environment you want to use for your project. See [environments](../guides/environments) for the full list. |
| `--message <message_str>` |    | Attach a message to the specific run of the project. |
| `--tensorboard` |   | Starts tensorboard in the environment. Tensorboard URL can be found in the dashboard. |
| command |      | Command to execute when running your project on Floyd. |

### Description
This command syncs the code tracked by the CLI to the Floyd servers and executes your command. You can see the progress
with [status](./status) command. To view the logs from your code use [logs](./logs) command.

### Example
```bash
$ floyd run "python train_tf.py -lr 0.01 -output /output/model.bin"
Syncing code ...
NAME
-----------------------------
floydhub/projects/tensorflow-project/7

...
$ floyd logs floydhub/projects/tensorflow-project/7
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

### Attaching multiple datasets

You can attach upto 5 datasets when you run a project using the run command. You can specify both
datasets you uploaded and output datasets of your previous runs. You can specify the mount point
also when you specify the data id to mount.

#### Example:
```bash
$ floyd run --data floydhub/datasets/cifar/1:training --data floydhub/datasets/faces/21:testing "python script.py"
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
Path to service endpoint: https://www.floydhub.com/expose/vbKSKgVYGgZqmM9i3LjLBb
```

{!contributing.md!}
