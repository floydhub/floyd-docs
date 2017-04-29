Floyd CLI is a python based command line tool to interact with FloydHub.

`floyd-cli` is available on [pypi](https://pypi.python.org/pypi/floyd-cli) and
runs on both Python 2.7 and Python 3.5.

Use pip to install the cli.

```bash
pip install -U floyd-cli
```

If successfully installed you can view the commands supported by the CLI using the 
`--help` option.

```bash
$ floyd --help
Usage: floyd [OPTIONS] COMMAND [ARGS]...

  Floyd CLI interacts with Floyd server and executes your commands. More
  help is available under each command listed below.

...
```

Detailed documentation for the floyd commands is available in the [documentation](../commands/index.md).

## Virtualenv

We highly recommend using [virtualenv](https://virtualenv.pypa.io/en/stable/userguide/) for 
installing floyd-cli. This helps to avoid any library version conflicts and results in smooth installation.

```bash
sudo pip install virtualenv
```

To create a virtualenv you need pass a path to store the virtualenv

```bash
virtualenv ~/floyd
```

You can activate the virtualenv by running:

```bash
source ~/floyd/bin/activate
```
Everytime you need to use floyd in a terminal, activate the virtualenv using the same command.

To install floyd-cli in this virtualenv:

```bash
pip install -U floyd-cli
```

Virtualenv has helped a large number of floyd users to have an easy install experience.

## Using sudo

If you are not using virtualenv and you are installing floyd globally you may need to use `sudo`:

```bash
sudo pip install -U floyd-cli
```

## Missing dependencies

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

and then try installing floyd-cli

## Python.h: No such file or directory

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
