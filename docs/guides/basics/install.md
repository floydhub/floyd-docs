!!! important "Quick Look"

    ## Using conda:

    ```
    $ conda install -y -c conda-forge -c floydhub floyd-cli
    ```

    ## Using pip:

    ```
    $ pip install -U floyd-cli
    ```

Floyd CLI (`floyd-cli`) is a Python-based command line tool to interact with FloydHub from your terminal.

`floyd-cli` is available on [pypi](https://pypi.python.org/pypi/floyd-cli) and [anaconda.org](https://anaconda.org/floydhub/floyd-cli) and
runs on Python 2.7, Python 3.5, and Python 3.6. `floyd-cli` works on Windows, MacOS, and Linux.

## Using `conda`:

```bash
$ conda install -y -c conda-forge -c floydhub floyd-cli
```


## Using `pip`:

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

### Having trouble?

If you had troubles with the above installation, consider using `virtualenv` to
install `floyd-cli`. This solves most users' installation issues. We've
detailed the process below.

## Using `virtualenv` to Install `floyd-cli`

If you aren't familiar with `virtualenv`, you can think of it as a way to
create totally fresh environments in which you can have a clean copy of Python
and install only the packages you need for working on a certain task or
project. You can turn these environments on and off as you need to use them.
This is useful because it helps you avoid issues that arise when you need more
than one version of the same package on your computer. If you'd like more
information on `virtualenv`, check out its [user
guide](https://virtualenv.pypa.io/en/stable/userguide/) or [this introductory
tutorial](http://www.pythonforbeginners.com/basics/how-to-use-python-virtualenv/)

We highly recommend using `virtualenv` for installing and using `floyd-cli`.
Because it helps avoid any library version conflicts, it results in a smoother
installation process. Using `virtualenv` solves most users' installation
issues.

### Step-by-step Process of Installing `floyd-cli` with `virtualenv`

Here is a step-by-step walkthrough of how to install `floyd-cli` using
`virtualenv`. First let's use `pip` to install `virtualenv`:

```bash
$ sudo pip install virtualenv
```

Create a virtualenv using the `virtualenv` command. You need to pass a path
where your environment will be located. This is both where all the information
about your virtualenv will be stored, as well as all of your virtualenv's
packages. Below, we use `~/floyd` as the path:

```bash
$ virtualenv ~/floyd
```
This will create a clean environment (a virtualenv) called `floyd` (named after
the folder we specified when we created the virtualenv).

You can now activate and start using the virtualenv by running:

```bash
$ source ~/floyd/bin/activate
```
When you want to use this virtualenv, you'll need to activate it using the same
`source ~/floyd/bin/activate` command. Each new terminal session will require
you to activate the virtualenv. To turn off the virtualenv, you can either exit your terminal session, or enter the `deactivate` command into your terminal.

After activating the virtualenv stored at `~/floyd`, your terminal prompt
should change to have `(floyd)` prepended to it. This serves as a reminder that
you have the `floyd` virtualenv turned on. Since our virtualenv is new, it
doesn't have any packages installed in it yet. Let's install `floyd-cli`:

```bash
(floyd) $ pip install -U floyd-cli
```

Success!

You are now ready to use the [floyd commands](http://docs.floydhub.com/commands/). Check out our [Quick Start tutorial](../../getstarted/quick_start) to get started using FloydHub and `floyd-cli`.

!!! important
    You need to activate your virtualenv using the `source ~/floyd/bin/activate`
    command above each time you open a new terminal and want to use `floyd-cli`
    in it.

## Having trouble installing the CLI?

See the list of [FAQs related to installation](../../faqs/installation.md).

{!contributing.md!}
