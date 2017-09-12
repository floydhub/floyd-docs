## Code
When developing locally, you keep your code together in a directory.
You might have a series of files and directories that make up your code. This
workflow stays the same when working with FloydHub. When you run a job on
FloydHub, your code will be pushed up to a powerful server designed for deep
learning. What will be different during the job is the location on the server
where your code will be running. Locally, your code is probably in a directory
like `/home/me/projects/my_project`, `/projects/python/dl/my_proj`,
`/Users/me/projects`. On the FloydHub server, your code will always be running
in a directory called `/code`. Most of the time, this doesn't change anything
for you. However, you may need to make some changes if your code uses relative
paths to find your data. For example, let's say that your project is in
`/home/me/projects/my_project`, and your data is in `/home/me/data/my_data`

The main things we need to be concerned with around code are how to initialize
a floyd "project", how to ignore files we don't want uploaded to the FloydHub
server each time we run a job, and how to make sure our code knows how and
where to access our data.

## Data
FloydHub's data workflow is the thing that feels most foriegn to new users who
are used to working on their local machine. When working on your local
machine, you might have your data in the same directory as your code, or in
another directory that your code references, and you likely have the location
of your data hardcoded in your code.

Datasets on FloyHub are stored completely separate from your code. When you run
a job, you can choose to attach up to five datasets to the job, and decide the
name of the directory where they will be located.

The main things you need to understand about data on FloydHub are how to upload
it and how to attach or "mount" it to a given job. Equally important to knowing
how to do those things is making sure that your code knows where to find your
data during a job. We'll cover that too.

## Environment
Locally, you've probably got a few different versions of Python and/or your
preferred deep learning libraries installed, etc. FloydHub has a myriad of
different deep learning environments to choose from, which already have these
dependencies installed, and have varying levels of hardware to meet your needs.
When you run a job on FloydHub, you'll be able to specify the environment you
want use, straight from the command line.

If FloydHub's stock deep learning environments don't meet your needs, you can
create a custom environment for your job. See **THIS GUIDE** for instructions
on that.

The main things you need to understand about environments on FloydHub are how
to specify which of the available environments you want to use for your job,
and how to customize your environment if the available environments don't meet
your needs.

## Output
Output is the way that you can link jobs together. You run a job to test an
idea. If it works, you may want to start where you left off and run
another job. If going down that path leads to a dead end, you may want to go
back to a previous output and start again from there. Knowing how to store
output is key to optimizing your deep learning workflow.

The main things you need to understand about output on FloydHub are how to
capture/save output from a job, and how to use it again in a future job.
Knowing this will allow you to successfully iterate on ideas and will make your
workflow much more efficient.

## Job
A job is what pulls together each of the above three pieces (code, data, and
environment), and actually gets the data science done. You run jobs using Floyd
CLI's `floyd run` command. The command has various flags and parameters that
let you customize how the job runs: What data do you want to use? Where should
the data be mounted on the server? What environment do you want to use? Should
the server run your job on a CPU or a GPU? What command(s) should the server
use to run your code? Any other commands you'd like to run on the server to set
it up before running your job? Etc.
