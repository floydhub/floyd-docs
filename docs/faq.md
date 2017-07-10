## Signup

### How does the free CPU / GPU hours work?

Every one who signups to Floydhub will receive 2 hours of free CPU / GPU time for running 
your projects. We hope this will give you enough time to evaluate Floydhub for your needs.
We are working on a new free plan right now to better help new users explore the platform.

### Is there a student discount?

Not at the moment, but we are currently working out a Student Plan. We will post the details 
very soon :)



## Login

### I get "Invalid Token" error on my Windows 10 machine when I run floyd login.

If you are using Windows command shell, there is an issue with pasting the token using the 
standard Ctrl + V. So you need to use the shell menu to paste the token. After copying the 
token right click on the top bar of the command shell and select Paste. See image below:

![Windows 10 Login](../img/login_win_10.jpg)


### I still get the "Invalid Token" error after trying the above suggestion.

In some windows shells (like Git Bash) there is an extra space added to the token field
before you paste the token. So you need to backspace and clear out the field before pasting 
the token. So the steps are:

1. Type `floyd login` in the console.
2. From the Floyd web page, select the token and click on the "Copy to clipboard" button.
3. In the console, press "backspace" a few times to remove the extra characters from the token login prompt request.
4. Right click on the menu bar, and select "Edit", and then "Paste"
5. Then press "Enter"

You should be able to login successfully now. If it's still not working, please give it a try on powershell.

## Running Experiments

### Why does `floyd status` return an empty list even though I have several runs in my account?

Floyd CLI uses the project directory to store the run information (similar to git). So you need 
to be in the directory where you initialized the project and you should be able to see all your 
runs. You can also use the [web dashboard](https://www.floydhub.com/experiments) to view all your 
projects in one place.


### What do I do when I get "What do you do when you get “You are over the allowed limits for this operation. Consider upgrading your account”?

Floydhub currently allows only 5 active runs per user. If you require more concurrency, contact 
us from the [pricing](https://www.floydhub.com/pricing) page.


### I get "Too many open files" error when I run my project.

Floyd CLI throws this error when you have too many files in your current directory that needs to be uploaded. 
The actual limit depends on your OS / machine specs.

You can either:

1. Remove unnecessary files from the directory (like build directory, docs etc.) 
2. Add them to `.floydignore` file. Floyd CLI will just ignore these directories. 
See the [floydignore](home/floyd_ignore) documentation to understand how this can be configured.
3. Tar them into a single file and untar them at runtime.

Alternatively, instead of uploading files from your local machine, you can also 
[download files](http://docs.floydhub.com/home/using_datasets/#creating-a-dataset-from-downloads) from a remote URL 
directly into Floyd servers.


### I ran my project in Jupyter mode but the url does not seem to work.

Jupyter notebook server takes a couple of minutes to start. Until then you will get a "Bad Gateway" 
or similar error when you access the URL. You can check the status of the Jupyter notebook 
by running the [logs](../commands/logs) command.


### Am I using the GPU instance by default?

Jobs are run on CPU instances by default. You can specify `--gpu` to run them on GPU instances.


### My job is taking a while to "sync changes". How do I make it go faster?

Floyd CLI uploads *all* the files in your current directory before starting your experiment.
There are a few ways to make this go faster:

1. Remove unnecessary files from the directory (like build directory, docs etc.) 
2. Add sub-directories to `.floydignore` file. Floyd CLI will ignore and not upload these sub-directories.
See the [init](../commands/init#description) command to understand how this can be configured.
3. If you have large data files consider uploading them separately as a [data source](../commands/data). 
You can then [refer](../home/using_datasets#using-data-set-in-experiments) to them in your project.


### My job finished but how I do I see my output?

You can use the floyd [output](../commands/output) command to view the output of your 
project. If you want to use this output in your next run view [this guide](../home/managing_output)


### Do I have to pay for the entire time my Jupyter Notebook is running?

Unfortunately, yes. As much as we would like to, we are unable to charge you only for the *computation time*. 

This is an engineering challenge. When you start a Jupyter Notebook instance and start executing commands, 
your state is maintained in memory (both CPU and GPU memory). So the instance has to be alive for the 
entire duration of your notebook, not just when you are executing commands.

For example, when you execute `import tensorflow` 
command, Tensorflow will allocate the entire GPU memory to the current session and waits for the next command. This makes the instance unusable by anyone else, so we have to charge you for the duration your Notebook is alive.


## Billing

### What payment types do you accept?

Currently, we accept credit or debit cards, including Visa, MasterCard and American Express.

### Do you keep my credit card information?

No, we do not retain any credit card information. We use [Stripe](https://stripe.com/) to 
process payments.

### When will my credit card be charged?

You can see your billing due date in the `Usage` tab on your Floydhub dashboard.

{!contributing.md!}
