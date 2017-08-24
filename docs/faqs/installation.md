### Using virtualenv to install floyd-cli

We highly recommend using [virtualenv](https://virtualenv.pypa.io/en/stable/userguide/) for installing and using `floyd-cli`. This helps avoid any library version conflicts and results in a smoother installation process.

```bash
sudo pip install virtualenv
```

To create a virtualenv, you need to pass a path to store the installed packages.

```bash
virtualenv ~/floyd
```

You can now activate and start using the virtualenv by running:
```bash
source ~/floyd/bin/activate
```

To install floyd-cli in this virtualenv:

```bash
pip install -U floyd-cli
```

You are now ready to use the [floyd commands](). Note: You need to activate your virtualenv using the `source` command above each time you open a new terminal and want to use `floyd-cli` in it.

### Using conda to install floyd-cli

If you are using Anaconda Python, you can also use `conda` to install `floyd-cli`, instead of `virtualenv`. 

```bash
conda create -n <insert-your-env-name-here>
source activate <insert-your-env-name-here>
pip install -U floyd-cli
```

Please see [this guide](https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/) on creating virtual environments for Python with conda.

### Using sudo to install floyd-cli

Try this if you see a permission error, such as `Permission denied` or `Access is denied`. If you are not using virtualenv and you are installing `floyd-cli` globally you may need to use `sudo`:

```bash
sudo pip install -U floyd-cli
```


### Dealing with missing dependencies when installing floyd-cli

Not all python environments are installed the same way. So sometimes you may run 
into install issues. If `pip` cannot install dependencies itself, you may see errors like:

```bash
...
Failed building wheel for scandir
...
```

or

```bash
...
No distributions matching the version for backports.tempfile (from floyd-cli)
...
```

In such cases, you can install the dependencies directly:

```bash
pip install -U scandir
pip install -U backports.tempfile
```

and then try installing `floyd-cli`.


### Python.h: No such file or directory

If you get this error in a linux environment:

```bash
...
Python.h: No such file or directory
```

you need to install `python-dev` package

```bash
sudo apt-get install python-dev
```


{!contributing.md!}