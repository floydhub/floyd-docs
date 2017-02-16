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

## Using data set in experiments

To use a public or your presonal dataset in your project you can use 
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
