# Jupyter Notebook

[Jupyter](http://jupyter.org/) or [IPython](https://ipython.org/) is an open source project that allows you 
to create and share documents that contain live code, equations, visualizations and explanatory text. This 
guide will show you how to run a Jupyter notebook on Floyd.

### Setup project

Clone a project which contain deep learning jupyter notebooks. For 
example: [aymericdamien/TensorFlow-Examples](https://github.com/aymericdamien/TensorFlow-Examples).
Then initialize a floyd project inside that.

```bash
$ cd TensorFlow-Examples/notebooks/3_NeuralNetworks
$ floyd init neural-networks
```

### Run in Jupyter mode

Floyd [run](#run) command has a `jupyter` mode. This will run upload the jupyter notebooks in the current 
directory and start a jupyter server for you.

```bash
$ floyd run --mode jupyter
Syncing code ...
RUN ID                  NAME                          VERSION
----------------------  --------------------------  ---------
dMoDZaCcvQMyfNbgwTx9f8  floydhub/neural-networks:1          1

Path to jupyter notebook: https://www.floydhub.com:8000/EQDsTpeqB3RkjpHUgBGDyB

To view logs enter:
    floyd logs dMoDZaCcvQMyfNbgwTx9f8
```

You can open the link to your jupyter notebook. The notebooks should be available and you can run 
any of them.

![Jupyter](img/jupyter_home.png)

### Selecting the environment

Jupyter notebooks also run in the same environments as other jobs. You can select any environment you want 
along with the `--env` parameter of the [run](#run) command. You can see the list of supported environments
[here](#environments).

```bash
$ floyd run --mode jupyter --env tensorflow_py2
Syncing code ...
```

### Additional dependencies

If you have any additional python dependencies, you can also add a `floyd_requirements.txt` file to 
the notebook directory before floyd run. The packages specified there will be installed before running the 
jupyter server


### Saving Jupyter Notebooks

Floyd does not save your Jupyter notebooks after you stop the floyd job. So you need to download any 
relevant notebooks by selecting `File > Download as` menu from the Jupyter notebook.

### Stopping the job

Once you have experimented with your code, you still need to stop the job. Run the [stop](#stop) command 
for this.
