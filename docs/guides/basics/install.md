Floyd CLI is a Python-based command line tool to interact with FloydHub from your terminal.

`floyd-cli` is available on [pypi](https://pypi.python.org/pypi/floyd-cli) and
runs on both Python 2.7 and Python 3.5.

Use `pip` to install the CLI.

```bash
$ pip install -U floyd-cli
```

Use `pip3` if you only want to install the CLI for Python 3:

```bash
$ pip3 install -U floyd-cli
```

After installation you can view the commands supported by the CLI using the
`--help` option.

```bash
$ floyd --help
Usage: floyd [OPTIONS] COMMAND [ARGS]...

  Floyd CLI interacts with Floyd server and executes your commands. More
  help is available under each command listed below.

...
```

Detailed documentation for the floyd commands is available in the [documentation](../../commands/index.md).

## Using virtualenv to install floyd-cli

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

You are now ready to use the [floyd commands](http://docs.floydhub.com/commands/). Note: You need to activate your virtualenv using the `source` command above each time you open a new terminal and want to use `floyd-cli` in it.

## Having trouble installing the CLI?

See the list of [FAQs related to installation](../../faqs/installation.md).

{!contributing.md!}
