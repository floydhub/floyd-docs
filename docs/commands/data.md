
Manage your data sets on Floyd. The subcommands are:

| Command              | Description              |
| -------------------  | ------------------------ |
| floyd data init      | Initialize a new dataset |
| floyd data upload    | Create a new dataset by uploading data |
| floyd data status    | List all your datasets  |
| floyd data delete    | Delete your datasets |
| floyd data output    | View contents of a dataset |

## floyd data init 

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
dataset at the current directory and tracks all files and subdirectories. These files will be uploaded when you run [upload](#floyd-data-upload).

The init command also creates a `.floydignore` file. Any files and directories you do not want Floyd to track can be added 
to this file. When you upload this dataset to Floyd, these files will not be uploaded.

### Example
Initialize a floyd dataset in your data directory.
```bash
$ cd /data/mnist
$ floyd data init mnist-data
Data source "mnist-data" initialized in current directory
```

---------------------------------

## floyd data upload

Upload a new dataset

### Usage
```bash
floyd data upload
```

### Description
Upload contents of the current directory as a new dataset. This data can now be referred to in the [run](./run.md) command.
At run time the data will be available at the `/input` path.

Floyd also versions your data so you can choose any specific version to use in your runs.

### Example
```bash
$ floyd data upload
Creating data source. Uploading files ...
DATA ID                 NAME                    VERSION
----------------------  --------------------  ---------
GY3QRFFUA8KpbnqvroTPPW  alice/mnist-data:1            1
```
Floyd will generate a data id for the uploaded dataset. This uploaded dataset can be used in your future experiments, if needed,
using this data id. See [here](../home/using_datasets/#using-data-set-in-experiments) for more details.

---------------------------------

## floyd data status

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

## floyd data delete

Delete datasets on FloydHub

### Usage
```bash
floyd data delete [OPTIONS] [IDS]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| IDS |      | One or more IDs of your data. |
| `--yes`, `-y` | False  | Skip delete confirmation step |

### Description
Deletes your datasets from FloydHub. This data will no longer 
be accessible. You can use the same command to delete output 
data as well.

Note: You do *not* have to be in the project directory to run this command.

#### Example
```bash
$ floyd data delete HYLEc2czGKRpYVm7rGtBoY qNcS5bXHtFdSiMZ35kkEPh
Delete Data: floydhub/mnist:1/output? [y/N]: y
Data deleted
Delete Data: floydhub/csr:7? [y/N]: y
Data deleted
```

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
| ID |      | ID of your data. |

### Description
The output command gives the url to access a dataset. This command by default opens the data url in your default browser.

### Example
```bash
$ floyd data output dTe2cJJrNR2CBD74rSZXPA
Opening output directory in your browser ...
```
