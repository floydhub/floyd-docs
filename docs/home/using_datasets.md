## Data Sources

Floyd manages data separately from your code. If you want to provide input data to your code, 
you should upload your data sets separately. You can then use them when running your project.

## Uploading a new dataset

To upload a new dataset, use the floyd [data](../commands/data.md) command.
Create or navigate to the directory where the data resides and run `floyd data init` to initialize.

```bash
$ cd models/
$ floyd data init sent-data
Data source "sent-data" initialized in current directory
```
Then you can upload your dataset to Floyd.

```bash
$ floyd data upload
Creating data source. Uploading files ...
DATA ID                 NAME                    VERSION
----------------------  --------------------  ---------
GY3QRFFUA8KpbnqvroTPPW  alice/sent-data:1            1
```
Floyd will generate a data id for the uploaded dataset. This uploaded dataset can be used in your future experiments, if needed,
using this data id. Read below for details.


## Creating a dataset from downloads

In the case where your datasets are available on the internet, you can download them directly into 
Floyd. You can run your download script like any other job using the [run](../commands/run.md) command.
Just store the downloaded files to the `/output` directory.

```bash
# Make sure the downloaded files are stored in /output
$ floyd run "sh download_data.sh"
Syncing code ...
...

$ floyd logs -t GY3QRFFUA8KpbnqvroTPPW
...
2017-02-16 03:41:15,863 INFO Downloading files to /output:
2017-02-16 03:41:15,863 INFO Creating /output/Af4ssasdf.jpg
2017-02-16 03:41:15,863 INFO Creating /output/2aF2safs2.jpg
...
```
You can get the id of the output using the [info](../commands/info.md) command.

```bash
$ floyd info GY3QRFFUA8KpbnqvroTPPW
-----------  ----------------------------------------------------
Run ID       GY3QRFFUA8KpbnqvroTPPW
Output ID    VB9bF6vtyvrHLdUsFbUuvW
...
-----------  ----------------------------------------------------
```

Now you can use the `Output_ID` as the value for `--data` parameter when running your next experiment.

## Using data set in experiments

To use a public or your personal dataset in your project you can use 
the `--data` parameter in the floyd [run](../commands/run.md) command.
The data will be mounted and available in `/input` directory at project during run time.

```bash
$ floyd run --data GY3QRFFUA8KpbnqvroTPPW "ls -la /input"
Syncing code ...
...

$ floyd logs -t GY3QRFFUA8KpbnqvroTPPW
...
2017-02-16 03:41:15,863 INFO - -rw-r--r--  1 root root 4151 Feb 16 11:38 positive_sentences.txt
2017-02-16 03:41:15,863 INFO - -rw-r--r--  1 root root 4621 Feb 16 11:38 negative_sentences.txt
2017-02-16 03:41:15,863 INFO - -rw-r--r--  1 root root 7797 Feb 16 11:38 neutral_sentences.txt
...
```

## Attaching multiple datasets

You can attach upto 5 datasets when you run a project using the run command. You can specify both 
datasets you uploaded and output datasets of your previous runs. You can specify the mount point 
also when you specify the data id to mount.

For example: 
```bash
$ floyd run --data GY3QRFFUA8KpbnqvroTPPW:training --data 4T9bF6vtyvrHLdUsFbUumA:testing "python script.py"
```

The above datasets will be mounted at `/training` and `/testing` respectively.

In case you do not specify the mount points, it will be mounted at `/<ID>`. i.e., it will use its own
ID as the mount point.
