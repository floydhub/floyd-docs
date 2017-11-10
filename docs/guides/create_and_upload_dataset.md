## Create a new Dataset

A [Dataset]() is a collection of data. If you have used Github, datasets in
FloydHub are a lot like code repositories, except they are for storing and
versioning data.

To create a new Dataset, visit
[www.floydhub.com/datasets](https://www.floydhub.com/datasets) and click on the
"New Dataset" button on the top right hand corner.

![Create new dataset](../../img/create_new_dataset.jpg)

Give the dataset a name and an apt description.

The `Visibility` field indicates who can see your dataset. If you set it to
`Public`, anyone can see your dataset and data versions. If you are working on
an open source project, this is a great way to share and contribute to the
FloydHub community. If your data is proprietary, please select `Private`. This
will ensure that only you and your team will have access to this dataset.

The section below shows how to upload a dataset from your local machine. If your
data is available on the internet, you can can [create a dataset out of it directly](#download-large-datasets-directly-to-floydhub-from-the-internet).

## Upload a Dataset

Once you have created a dataset, you can upload data from your terminal using
the [floyd data](../../commands/data) command:

1. `floyd data init <dataset_name>`
2. `floyd data upload`

For example:

```bash
$ floyd data init imagenet-2017
Dataset "imagenet-2017" initialized in current directory
...
$ floyd data upload
Compressing data...
```

!!! note

    Depending on the size of your dataset and the speed of your internet
    connection, uploading a dataset can take a while.

### Resuming an Upload

Dataset uploads are resumable. If your Internet connection cuts out during an
upload, you'll be able to resume it later if you choose to.

If your upload has stopped before it completing, resume it using the `--resume`
or `-r` flag:

```
$ floyd data upload --resume
Uploading compressed data. Total upload size: 74.0MiB
[=                               ] 4194304/77626756 - 00:00:00
```

If you don't pass the `--resume` flag, but you have an unfinished upload, you
will be prompted to specify whether or not you'd like to resume the previous
upload:

```
$ floyd data upload
An unfinished upload exists. Would you like to resume it? [y/N]: N
Compressing data...
```

### Updating/Versioning Your Dataset

If you've made changes to your dataset and would like to upload it again, use
the following steps. You'll notice they are the same as uploading your dataset
the first time:

1. `cd` into your dataset's directory
2. Run `floyd data init <dataset_name>` to prepare to upload
3. Run `floyd data upload`

Your dataset will be versioned for you, so you can still reference the old one
if you'd like. Datasets will be named with sequential numbers, like this:

- mckay/datasets/foo/1
- mckay/datasets/foo/2
- mckay/datasets/foo/3
- ...

When using a dataset in a job, be sure to reference to the dataset version that
your job needs.

### Understanding the Upload Process

When you upload a dataset to FloydHub, Floyd CLI compresses and zips your data
before securely transferring it to FloydHub's servers over the Internet. Once
your dataset has been uploaded, FloyHub decompresses and unzips your dataset
for you. If you have a large dataset, unpacking your data on FloydHub's servers
can take a while.

You can check the status of your upload using `floyd data status` with the name
of your dataset, as shown below:

```
$ floyd data status mckay/datasets/mnist/1
DATA NAME                    CREATED        STATUS    DISK USAGE
---------------------------  -------------  --------  ------------
mckay/datasets/mnist/1       3 minutes ago  valid     82.96 MB
```

`valid` is the state you're looking for. That means that your dataset has finished being unpacked and is ready to use.

!!! warning "Good to Know"

    It will not save you time to compress your dataset before uploading it,
    since Floyd CLI already compresses your dataset to minimize upload time.

## Download large datasets directly to FloydHub from the internet

Often times, it might not be practical to upload datasets to FloydHub from your local machine. For example, your upload speeds might be too slow, or you just don't want to download a large dataset from the internet just to upload it again.

If your data is already available on the internet, then you can create a dataset directly on FloydHub.

### Step 1: Run a terminal on FloydHub servers using Jupyter mode

You can create a terminal session on FloydHub. Here are the quick steps:

- Run a Jupyter Notebook job using a CPU instance

```
$ floyd run --mode jupyter
```

- Once your Jupyter server starts, create a Terminal

![Jupyter Notebook Terminal Button](../img/jupyter_terminal_button.jpg)

- Once you're in the terminal, you'll automatically be in the `/output` directory, but you can always confirm with the `pwd` command. From here, you can download your data to your FloydHub instance.

Here is an example that downloads a CSV with details about members of the United States Congress

```
$ mkdir congress
$ cd congress/
$ wget https://theunitedstates.io/congress-legislators/legislators-current.csv
```

- Post process your data (if necessary)

For example, if the file that you downloaded is a tar file, you can untar it here. Or you can download multiple files and organize them here. Or you could open up a Jupyter notebook within this session and transform your data even further. Just make sure to clean up the `/output` directory so that only the files that you want in your dataset are present there.

```
Untar the files to the current dir

$ tar xvzf train-images-idx3-ubyte.gz

Remove the tar file

$ rm -rf train-images-idx3-ubyte.gz

Ensure that only the files you want are present in `/output`

$ ls /output

```

### Step 2: Stop the Jupyter Notebook session and create a dataset from the job's output

Navigate to your current job's page on FloydHub and click the Cancel button to stop this active Jupyter session. Once the job has been shut down, you can click the `Create Dataset` button on the `Output` tab to open a modal that will help you turn this output into a FloydHub dataset.

![Job Output Page](../img/output.png)

The modal will ask if you'd like to copy this output to one of your existing datasets or create a new dataset entirely.

![Create Dataset Modal](../img/modal.png)

Click the `Create Dataset from Output` button once you're ready, and you'll be navigated to your newly created Dataset on FloydHub.




