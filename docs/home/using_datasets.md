## Data Sources

Floyd manages data separately from your code. You can upload your data sets 
separately and use them when running your project.

## Uploading a new dataset

To upload a new dataset, use the floyd [data](../commands/data.md) command.
Create or navigate to the directory where the data resides and run `floyd data init` to initialize.

```bash
$ cd models/
$ floyd data init data-model
Data source "data-model" initialized in current directory
```
Then you can upload it to Floyd.

```bash
$ floyd data upload
Creating data source. Uploading files ...
DATA ID                 NAME                    VERSION
----------------------  --------------------  ---------
GY3QRFFUA8KpbnqvroTPPW  alice/data-model:1            1
```
Floyd will generate a data id for the uploaded dataset. This uploaded dataset can be used in your future experiments, if needed,
using this data id. Read below for details.

## Using data set in experiments

To use a public or your presonal dataset in your project you can use 
the `--data` parameter in the floyd [run](../commands/run.md) command.
The data will be available in `/input` directory at project run time.

```bash
$ floyd run --data GY3QRFFUA8KpbnqvroTPPW "ls -la /input"
Syncing code ...
...
```
