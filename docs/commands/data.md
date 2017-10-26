
Manage your data sets on Floyd. The subcommands are:

| Command              | Description              |
| -------------------  | ------------------------ |
| floyd data init      | Initialize a dataset |
| floyd data upload    | Create a new dataset version |
| floyd data status    | List all your datasets  |
| floyd data clone     | Clone an existing dataset |
| floyd data delete    | Delete your datasets |
| floyd data add       | Add job output to dataset | 
| floyd data output    | View contents of a dataset |

## floyd data init 

Initialize a Floyd dataset.

### Usage
```bash
floyd data init DATASET_NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| DATASET_NAME    |         | Name of the dataset (Pick a name from the dataset page in web dashboard)    |

### Description
Floyd can manage your experiment datasets and make them available when running your projects.This command initializes the 
current directory and tracks all files and subdirectories. Make sure the dataset name you enter here already 
exists in Floyd. In case the dataset name does not exist, the CLI will open the create dataset page in your browser.

### Example
Initialize a floyd dataset in your data directory.
```bash
$ cd /data/mnist
$ floyd data init mnist-data
Data source "mnist-data" initialized in current directory
```

---------------------------------

## floyd data upload

Upload a new version of dataset

### Usage
```bash
floyd data upload
```

### Description
Upload contents of the current directory as a new version of the dataset. This data can now be referred to in the [run](./run.md) command.
At run time the data will be available at the `/input` path.

Floyd also versions your data so you can choose any specific version to use in your runs.

Currently this command does NOT respect a `.floydignore` file. This functionality may be added in the future.

### Example
```bash
$ floyd data upload
Creating data source. Uploading files ...
NAME
--------------------
alice/mnist-data:1  
```
Floyd will generate a data id for the uploaded dataset. This uploaded dataset can be used in your future experiments, if needed,
using this data id. See [here](../guides/data/mounting_data/#mounting-datasets) for more details.

---------------------------------

## floyd data status

View your datasets on Floyd

### Usage
```bash
floyd data status [NAME or ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| NAME or ID |      | Name or ID of your data. |

### Description
Lists all your datasets on Floyd with more details.

#### Example
```bash
$ floyd data status
DATA NAME                         CREATED         STATUS    DISK USAGE
--------------------------------  --------------  --------  ------------
alice/datasets/mnist-data/2       57 seconds ago  valid     180.0 KB
alice/datasets/mnist-data/1       2 minutes ago   valid     10.0 KB
```

---------------------------------

## floyd data delete

Delete datasets on FloydHub

### Usage
```bash
floyd data delete [OPTIONS] [NAMES or IDS]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| NAMES or IDS |      | One or more Names or IDs of your data. |
| `--yes`, `-y` | False  | Skip delete confirmation step |

### Description
Deletes your datasets from FloydHub. This data will no longer 
be accessible.

Note: You do *not* have to be in the project directory to run this command.

#### Example
```bash
$ floyd data delete floydhub/datasets/csr/7
Delete Data: floydhub/datasets/csr/7? [y/N]: y
Data deleted
```

---------------------------------

## floyd data add

Copy job output data to a dataset

### Usage
```bash
floyd data add ID
```

### Description
Add the contents of a job output to a dataset. This will appear as a new version of data in the dataset. This command is useful if you 
want to save the output of specific jobs under a dataset. Note: You will be charged for the disk usage separately.
This new data can now be referred to in the [run](./run.md) command.

### Example
```bash
$ floyd data add alice/projects/mnist/1/output
DATA NAME                         CREATED    STATUS    DISK USAGE
--------------------------------  ---------  --------  ------------
alice/datasets/mnist-data/3       just now   valid     10.0 KB
```
Floyd will generate a new version for the added data. This can be used in your future experiments, if needed,
using this data id. See [here](../guides/data/mounting_data/#mounting-datasets) for more details.

---------------------------------

## floyd data output

View datasets

### Usage
```bash
floyd data output [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL. The data directory can be viewed in the browser. |
| NAME or ID |      | NAME or ID of your data. |

### Description
The output command gives the url to access a dataset. This command by default opens the data url 
in your default browser.

### Example
```bash
$ floyd data output floydhub/datasets/csr/11
Opening output directory in your browser ...
```

{!contributing.md!}
