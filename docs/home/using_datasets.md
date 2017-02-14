## Data Sources

Floyd manages data separately from your code. You can upload your data sets 
separately and use them when running your project.

## Uploading a new dataset

To upload a new dataset, use the floyd [data](../commands/data.md) command.
Create a directory with the data and initialize it for data.

```bash
$ cd /data/mnist
$ floyd data init mnist-data
Data source "mnist-data" initialized in current directory
```
Then you can upload it to Floyd

```bash
$ floyd data upload
Creating data source. Uploading files ...
```

## Using data set in runs

To use a public or your presonal dataset in your project you can use 
the `--data` parameter in the floyd [run](../commands/run.md) command.

```bash
$ floyd run --data dTe2cJJrNR2CBD74rSZXPA "python train_tf.py -lr 0.01 -output /output/model.bin"
Syncing code ...
...
```

The attached data set will be available at `/input` at project runtime.
