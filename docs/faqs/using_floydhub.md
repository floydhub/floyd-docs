### How can I automate a process that involves FloydHub?

We have a python SDK that can be used to automate your FloydHub workflow. The *sdk is in alpha* - so we are giving access to folks who are interested in using this and giving feedback. If you need any features, we are happy to work with you on that. Let us know if you are interested in alpha testing the sdk.

You can also see how one of our customers automated their FloydHub workflow in our [blog post](https://blog.floydhub.com/automate-floydhub-with-celery/).

### How can I ssh into the remote machine?

We don't support ssh access to the remote instance at the moment. However, you can connect to the machine using your browser: [Workspaces](../guides/workspace) are interactive environments where you can run notebooks and scripts. You will also have [terminal](../guides/workspace/#using-terminal) access here.

### Can I close my laptop during the training?

#### Command jobs
When you submit [command jobs](../guides/run_a_job/), your code is uploaded to FloydHub and training is started in the cloud. You can close the browser or shutdown your machine and the job running in the cloud will not be affected. You can monitor the job anytime from the website and view the logs and metrics in realtime. When the training script ends it will be shutdown automatically by FloydHub.

#### Workspaces
[Workspaces]((../guides/workspace)) are interactive development environment. You can run jupyter notebooks and python scripts here. When running jupyter notebooks, you have to keep your browser tab open and connected to the internet to receive the output of your code cells. If you close your browser when your code cell is executing, you will lose the output printed by the cell but the code will continue to run. When you re-open the browser tab, the output of the code cell will be empty.

This is an artifact of Jupyter Notebooks:

"Anything already running in the notebook will keep running, and the kernel it started for that will stay running - so it won't lose your variables. However, any output produced while the notebook isn't open in a browser tab is lost; there isn't an easy way to change this until we have the notebook server able to track the document state, which has been on the plan for ages."

#### Workarounds

Here are some workarounds that you can use:

- Send all the output of your jupyter notebook to a log file that you can inspect anytime.
- Send metrics to [Tensorboard](../guides/jobs/tensorboard/) - this way you will be able to view the training results later even if the code cell output is lost.
- Convert your notebook to a python script and run the Job in command mode.

### Which type of machines do you provide?

CPU and CPU2 machines do not have a GPU.
GPU and GPU2 machines will come with both CPU and GPUs.

Here is the full list of all the machine types we offer and the hardware specifications:

![CPU, CPU2, GPU and GPU2 specs](../img/faqs_using_fh/powerups.png)

You can find the price for each machine in the [pricing page](https://www.floydhub.com/pricing#powerups).

We are also planning to introduce new machines soon (multi-gpus, TPUS etc...). If you need a custom setup, please reach us via the chat bubble or email us at support@floydhub.com.

### Where is your datacenter located?

We have only a datacenter that is located in Oregon, USA.

![Oregon, USA map](../img/faqs_using_fh/Oregon.png)

We have plans to add new datacenters in Europe and Asia in the future. Let us know if you need that for your projects.
