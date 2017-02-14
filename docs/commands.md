# Floyd Commands

Below are the commands that are part of Floyd CLI.

| Command            | Description              |
| ------------------ | ------------------------ |
| floyd login        | Login to Floyd. |
| floyd init         | Initialize a Floyd project |
| floyd run          | Run your project on Floyd. |
| floyd data         | Manage data on Floyd   |
| floyd logs         | Stream logs of your run |
| floyd status       | Check status of your jobs |
| floyd output       | View the output of a job |
| floyd info         | See details of a job   |
| floyd stop         | Terminate a job   |


---------------------------------
## floyd login

Login to Floyd.

### Usage
```bash
floyd login
```

### Description
You need to login to Floyd before running any other command. The login flow will require an access token from the Floydhub 
website. You will be prompted to enter you credentials to see your access token. Copy and past the token on the command line 
to complete login.

### Example
```bash
$ floyd login
Access token page will now open in your browser. Continue? [Y/n]:
Please paste the code here:
Login Successful
```
---------------------------------
## floyd init

Initialize a Floyd project.

### Usage
```bash
floyd init PROJECT_NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| PROJECT_NAME    |         | Name of your project (No spaces. Use letters, numbers, dash and underscore)    |

### Description
Floyd tracks projects based on the location of your code. This command initializes a new project at the current directory and 
tracks all files and subdirectories. These files will be uploaded when you run your project on Floyd.

The init command also creates a `.floydignore` file. Any files and directories you do not want Floyd to track can be added 
to this file. When you run your project on Floyd, these files will not be uploaded.

### Example
Initialize a floyd project in your project directory.
```bash
$ cd /code/project
$ floyd init style-transfer
Project "style-transfer" initialized in current directory
```

---------------------------------
## floyd run

Run your project on Floyd.

### Usage
```bash
floyd run [OPTIONS] [COMMAND]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--gpu/--cpu` |  cpu    | If specified, runs the job on a GPU (G1) instance or CPU (C1) instance. See instance specifications on the [pricing](https://www.floydhub.com/pricing) page. |
| `--data <ID>` |    | ID of the data source to link to. See [data](#data) section for more details. |
| `--mode [command|jupyter|serving]` |  command  | Specify the mode you want to run the project. The default behavior executes the command you specify. See [jupyter](#jupyter) and [serving](#serving) sections for more info on them. |
| `--env [tensorflow_py3|tensorflow_py2]` | tensorflow_py3  | Specify the environment you want to use for your project. See [environments](#environments) for the full list. |
| command |      | Command to execute when running your project on Floyd. |

### Description
This command syncs the code tracked by the CLI to the Floyd servers and executes your command. You can see the progress 
with [status](#status) command. To view the logs from your code use [logs](#logs) command.

#### Example
```bash
$ floyd run "python train_tf.py -lr 0.01 -output /output/model.bin"
Syncing code ...
RUN ID                  NAME                           VERSION
----------------------  ---------------------------  ---------
dTe2cJJrNR2CBD74rSZXPA  floydhub/tensorflow-project:7        7
...
$ floyd logs dTe2cJJrNR2CBD74rSZXPA
```

#### floyd_requirements.txt
Floyd runs standard Docker images for various deep learning frameworks.(See [environments](#environments) for details). If your 
code requires additional Python dependencies you can specify them in a `floyd_requirements.txt` file and place it at the root 
directory of your project. These dependencies will be installed before running your code.

#### Example
```bash
$ cat floyd_requirements.txt
Pillow
scipy
$ floyd run "python train_tf.py -lr 0.01 -output /output/model.bin"
```
#### Jupyter notebook
Floyd supports running Jupyter/iPython notebooks on the server. Make sure that the notebook (.ipynb) files are present in the 
current directory. Use `--mode jupyter` and you will be presented with a URL to view your Jupyter environment. You do not need 
to specify a command in this mode. See [jupyter](#jupyter) page for more details.

#### Example
```bash
$ floyd run --mode jupyter
...
Path to jupyter notebook: https://www.floydhub.com:8000/g8uGRZFQz85meArJGToEcs
```
#### Serving
Floyd can be used to host the model you generated as a REST api. This api can be used to evaluate your model over HTTP.
Use `--mode serving` and you will be presented with a URL to access your API. Floyd currently supports only Flask apps.
It runs app.py file and expects the service to run on port 5000. You do not need to specify a command in this mode.
See [serving](#serving) page for more details.

#### Example
```bash
$ floyd run --mode serving
...
Path to service endpoint: https://www.floydhub.com:8000/vbKSKgVYGgZqmM9i3LjLBb
```
---------------------------------

## floyd data

Manage your data sets on Floyd. The subcommands are:

| Command            | Description              |
| ------------------ | ------------------------ |
| floyd data init    | Initialize a new dataset |
| floyd data upload  | Create a new dataset by uploading data |
| floyd data status  | List all your datasets  |
| floyd data output  | View contents of a dataset |

---------------------------------

### floyd data init

Initialize a new dataset.

### Usage
```bash
floyd data init DATASET_NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| DATASET_NAME    |         | Name of the dataset (No spaces. Use letters, numbers, dash and underscore)    |

### Description
Floyd can manage your experiment datasets and make them available when running your projects.This command initializes a new 
dataset at the current directory and tracks all files and subdirectories. These files will be uploaded when you run [upload](#upload).

The init command also creates a `.floydignore` file. Any files and directories you do not want Floyd to track can be added 
to this file. When you upload this dataset to Floyd, these files will not be uploaded.

### Example
Initialize a floyd data in your project directory.
```bash
$ cd /data/mnist
$ floyd data init mnist-data
Data source "mnist-data" initialized in current directory
```

---------------------------------

### floyd data upload

Upload a new dataset

### Usage
```bash
floyd data upload
```

### Description
Upload contents of the current directory as a new dataset. This data can now be referred to in the [run](#run) command.
At run time the data will be available at the `/input` path.

Floyd also versions your data so you can choose any specific version to use in your runs.

### Example
```bash
$ floyd data upload
Creating data source. Uploading files ...
```
---------------------------------

### floyd data status

View your datasets on Floyd

### Usage
```bash
floyd data status [ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your data. |

### Description
Lists all your data sets on Floyd with more details.

#### Example
```bash
$ floyd data status
DATA ID                 CREATED         DISK USAGE    NAME                                        VERSION
----------------------  --------------  ------------  ----------------------------------------  ---------
HYLEc2czGKRpYVm7rGtBoY  12 minutes ago  372.0 MB      floydhub/mnist:1                                  1
qNcS5bXHtFdSiMZ35kkEPh  an hour ago     456.2 MB      floydhub/csr:7                					7
```
---------------------------------

### floyd data output

View datasets

### Usage
```bash
floyd data output [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL. The data directory can be viewed in the browser. |
| ID |      | ID of your data. |

### Description
The output command gives the url to access a dataset. This command by default opens the data url in your default browser.

### Example
```bash
$ floyd data output dTe2cJJrNR2CBD74rSZXPA
Opening output directory in your browser ...
```

---------------------------------

## floyd logs

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
| ID |      | ID of your job. You can get the ID by running the [status](#status) command.    |

### Description
Any data sent to STDOUT and STDERR by your code will become available here. Make sure your 
logs are flushed out if you prefer to view logs in real-time. There will be some information from 
Floyd servers before and after your project logs. They are usually useful for debugging purposes.

### Example
```bash
$ floyd logs qYPdvbE5KS3TwANJFZdame
Preparing to run 
Starting container...

#################################################

Run Output:
...

#################################################

Waiting for container to complete...
[success] Finishing execution
```

---------------------------------

## floyd status

View status of your jobs.

### Usage
```bash
floyd status [ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job. |

### Extended Description
Shows the status of a run, if the ID is specified. It can also list the status of all 
the runs in the current project. You need to be in the project directory for this command to work.

#### Example
```bash
$ floyd status
RUN ID                  CREATED         STATUS      DURATION(s)  NAME                           INSTANCE      VERSION
----------------------  --------------  --------  -------------  -----------------------------  ----------  ---------
dTe2cJJrNR2CBD74rSZXPA  31 minutes ago  success             108  floydhub/tensorflow-project:7  cpu                 2
B8wkLbuGs2mtjhe9jqrkYT  2 hours ago     success            2349  floydhub/tensorflow-project:7  gpu                 1
```

---------------------------------

## floyd output

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

---------------------------------

## floyd info

View the details of the job.

### Usage
```bash
floyd info [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job. You can get the ID by running the [status](#status) command.    |

### Description
This command gives detailed information about your job. Some useful information here:

#### Output ID
Output ID is the reference to the output generated by your run. If you want to use this as the 
input for your next job, use this ID and pass it as `--data ID` in the [run](#run) command.

#### Url
If your job is running in [jupyter](#jupyter) or [serving](#serving) mode, you can get their URL here.

### Example
```bash
$ floyd info Faa2xpokjAfJL5Jd7vCVXo
-----------  ----------------------------------------------------
Run ID       Faa2xpokjAfJL5Jd7vCVXo
Name         floydhub/jupyter-notebook:1
Created      2 minutes ago
Status       running
Duration(s)  0
Output ID    VB9bF6vtyvrHLdUsFbUuvW
Instance     cpu
Version      1
Mode         jupyter
Url          https://www.floydhub.com:8000/VB9bF6vtyvrHLdUsFbUuvW
-----------  ----------------------------------------------------
```

---------------------------------
## floyd stop

Terminate a queued or running job.

### Usage
```bash
floyd stop ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job. You can get the ID by running the [status](#status) command.    |

### Description
Sometimes you want to terminate a job before it can finish. The stop command sends a request 
to the server to stop the job. You can view the [status](#status) of the job to confirm. When you stop 
a job, you will be charged only for the duration your job was running.

### Example
```bash
$ floyd stop FAGrKvd6GqwVdHMxxMwBZG
Experiment shutdown request submitted. Check status to confirm shutdown
```
---------------------------------
## floyd logout

### Description
Logout the CLI from Floyd 

### Usage
```bash
floyd logout
```

---------------------------------
