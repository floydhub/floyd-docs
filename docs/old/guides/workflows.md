This guide will walk you through some common workflows on Floyd.

## Download and Train

In this workflow, you are:

1. Downloading the training data from the internet
2. Pre-process the data
3. Train a model
4. Evaluate the model
5. Expose as an API

### Download the training data

You can download any data set from the internet using `wget`. Just make sure to 
store the data to `/output`.

```bash
$ floyd run "wget -O full_data.zip https://dataset.com/full_data.zip"
Syncing code ...
RUN ID                  NAME                              VERSION
----------------------  ------------------------------  ---------
DJSdJAVa3u7AsFEMZMBBL5  floydhub/download-data:1                1
```

Wait for the job to be finished successfully and then check the output. You should 
see the zip file in the directory.

```bash
$ floyd output DJSdJAVa3u7AsFEMZMBBL5
Opening output directory in your browser ...
```

Now record the Output ID:

```bash
$ floyd info DJSdJAVa3u7AsFEMZMBBL5
-----------  ----------------------------------------------------
Run ID       DJSdJAVa3u7AsFEMZMBBL5
Name         floydhub/download-data:1
Output ID    VB9bF6vtyvrHLdUsFbUuvW
-----------  ----------------------------------------------------
```


### Pre-process data

You want to unzip the downloaded data, split it in to training and test data.


{!contributing.md!}
