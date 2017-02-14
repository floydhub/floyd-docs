# Get Started

To get started with Floyd, you can use the Floyd CLI to 
run Tensorflow and Keras experiments and view the output.

### Installing Floyd CLI

See [here](docs/installation) for install instructions of 
Floyd CLI.

### Creating an account

If you don't have an account already, visit the Floyd 
website(https://beta.floydhub.com/signup) to create one.

You can also try out the tool with a temporary demo account.

### Logging in to Floyd

You need to first login to the Floyd server. Use the login 
command for that.

    $ floyd login
    Username: alice
    Password:
    Login Successful

You need to do this only once across all your projects.

### Creating a new project

To create a new project, go to the directory that has the 
tensorflow code to run. If you do not have any code handy, you 
can clone an examples repo from github.

    $ git clone https://github.com/floydhub/tensorflow-examples.git
    Cloning into 'tensorflow-examples'...
    $ cd tensorflow-examples

Now initialize a new Floyd project with the `init` command and 
choose a project name.

    $ floyd init
    Project: tf-demo
    Project tf-demo initialized in current directory

Now you are ready to run your first project on Floyd!

### Running your project on Floyd

Running your project on Floyd is very straightforward. It is very similar 
to running on your computer. Let us run one of the python files in 
the examples repo

    $ floyd run python 1_Introduction/helloworld.py
    Creating module. Uploading 20 files ...
    RUN ID                  NAME                 VERSION
    ----------------------  -----------------  ---------
    mBDHCqro9Hd2dHTYdRReGd  alice/tf-demo:1          1

Congratulations! your first experiment is now running on Floyd. 
Store the `RUN ID` for future commands.

### Viewing logs of your run

You may now want to view the logs of the experiment you just kicked off. 
Use the `logs` command for that.

    $ floyd logs mBDHCqro9Hd2dHTYdRReGd
    ...
    ################################################################################

    2017-01-20 19:18:41,353 INFO - Run Output:
    2017-01-20 19:18:42,306 INFO - b'Hello, TensorFlow!'
    2017-01-20 19:18:42,447 INFO -
    ################################################################################
    ...

You can see the output of your code in the `Run Output` section of the logs.
Any thing you log or print in your code will appear here.

### Check the status of your runs

To see the status of your experiments, use the `status` command. You can specify 
a single `RUN ID` to get its status. Otherwise the CLI will show the results of 
all your experiments in that project.

    $ floyd status
    RUN ID                  CREATED        STATUS      DURATION  NAME               INSTANCE      VERSION
    ----------------------  -------------  --------  ----------  -----------------  ----------  ---------
    ncGPzDrm7XV58pBeKGUxd6  just now       success            3  alice/tf-demo:2     cpu                 2
    mBDHCqro9Hd2dHTYdRReGd  4 minutes ago  success            4  alice/tf-demo:1     cpu                 1

### Re-running your project

If you would like to edit your code an re-run your project, you just use the `run`
command again. The CLI will upload the new version of your code and start another 
experiment.

### Storing output files

Most of the experiments generate output like model files. In Floyd, any file 
or directory you create under `/output/` directory at run time will be available 
to you for download after the experiment finishes.

An example command for this:

    $ floyd run "python 1_Introduction/helloworld.py > /output/tf-output.txt"
    Creating module. Uploading 20 files ...
    RUN ID                  NAME                 VERSION
    ----------------------  -----------------  ---------
    mBDHCqro9Hd2dHTYdRReGd  alice/tf-demo:3          3

The file created under `/output` will be saved.

### Viewing and downloading output files

To view the output files, you can use the `output` command of floyd.

    $ floyd output mBDHCqro9Hd2dHTYdRReGd
    Opening output directory in your browser ...

This will open the browser and direct you to the output directory. You will be able to view 
and download any file you prefer.

### Installing additional Python packages

Floyd by default runs on a docker image with `tensorflow-0.12.1` on `Python 3.5`.
If your code needs additional Python packages to be available at run time, you 
can add them to a `floyd_requirements.txt` file. This is a special file that 
will be read at runtime and the packages listed here will be installed before 
running your command.

    $ echo "keras" > floyd_requirements.txt

### Running on a GPU Instance

It is very easy to run your code on a GPU instance of Floyd. Just add `--gpu` flag 
to the floyd `run` command.

    $ floyd run --gpu "python 1_Introduction/helloworld.py > /output/tf-output.txt"
    Creating module. Uploading 20 files ...
    RUN ID                  NAME                 VERSION
    ----------------------  -----------------  ---------
    KYBMnXZo3DsGGCiRdcYNUc  narenst/tf-demo:4          4

Make sure your code is optimized to use the available GPU.
