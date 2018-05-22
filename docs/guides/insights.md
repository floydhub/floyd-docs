# Insights

Insights offer warning alerts about the condition of your FloydHub machine during an active Workspace session. Specifically, Insights are connected to the available System Metrics for your Workspace. For more information on System Metrics, please visit the [System Metrics](https://docs.floydhub.com/guides/jobs/metrics/#system-metrics) docs page.

Insights will be found in the bottom bar of your Workspace, indicated by a circle icon next to the name of the System Metric. Click on the Metric to open a chart of its values, along with a message about the Insight.

![Insights](../img/insight_alert.gif)

There are three levels of Insight (in ascending levels of severity):

#### Info (Amber dot)

![Info](../img/insight_info.png)

#### Warning (Red dot)

![Warning](../img/insight_warning.png)

#### Alert (Pulsing red dot)

![Insights](../img/insight_alert.gif)


!!! important "Beta feature"
    Insights is currently in beta and under active development. If you have feedback or feature requests, please let us know - via the chat bubble or email [support@floydhub.com](mailto:support@floydhub.com)

### GPU Utilization

Insights for GPU Utilization indicate that you're under-utilizing your GPU during your Workspace session. As a result, you might want to optimize your training code to better utilize your GPU. For example, trying different batch size to saturate the GPU memory.

Alternatively, if you're still in active development, you might want to restart your workspace in CPU mode, and then only switch back to GPU when you're ready for the additional compute power.

In general, when you see this Insight, you might want to try:

- Increase the batch size
- Build a deeper model
- Debug your input data pipeline for possible bottleneck.

Also, for some tasks, it is fine to not exceed the 70% of GPU capacity due to the nature of the particular computation / experiment. For example, if you have an experiment which requires resource demanding pre / post-processing on CPU. In these cases, you can always ignore the Insight.

#### Why is my GPU usage is 0%?

Make sure that your framework support GPU acceleration. Please consult the framework docs for this.

Note that not all the operations can be placed on the GPU. Some framework provide an API for the device placement of each operations and variables -- this can be a really useful tool for debugging this issue. Please consult the framework docs for this.

!!! warning "Metrics frequency"
	If your computation is not intensive enough (e.g. training a shallow network for the MNIST task), it can fall below the sampling frequency of the Workspace's System Metric Collector (which samples once every 60 seconds).

!!! important "Real-time monitoring"
	For a more fine grained monitor solution of the resources required during the computation, our advice is to launch the `top` and `nvidia-smi -l 2` commands in two different terminal.

#### Info

GPU Utilization has been under 70% of capacity for the last five (5) minutes.

#### Warning

GPU Utilization has been under 70% of capacity for the last fifteen (15) minutes.

#### Alert

GPU Utilization has been under 80% of capacity for the last thirty (30) minutes.

### RAM (Memory) Utilization

Insights for RAM Utilization will indicate when your FloydHub's machine's RAM is getting close to its maximum, which could lead to Out-of-Memory Errors.

When you see this Insight, you might want to try:

- Reduce the number of samples to load in memory: use a subset of your data,
- Switch to an instance with more RAM (e.g. CPU2).

This Insight will consistently track the latest reported value of your machine's RAM.

#### Info

RAM Utilization is currently greater than 75%.

#### Warning

RAM Utilization is currently greater than 90%.

#### Alert

RAM Utilization is currently greater than 90%.

### Disk Utilization

Insights for Disk Utilization will indicate when your FloydHub machine is running low on disk space.

When you see this Insight, it could indicate that you've generated significant amounts of data that should be separated and broken out from your Workspace's codebase.

!!! Suggestion
	A Checkpoint Strategy with an high frequency and high number of checkpoints, even if really helpful to track normal and long training regime, require a great amount of disk usage. For more information on the different Checkpoint Strategy, please give a read to [Checkpoint Strategy](https://blog.floydhub.com/checkpointing-tutorial-for-tensorflow-keras-and-pytorch/) blog post.

This insight will consistently track the latest reported value of your machine's disk space.

#### Info

Disk Utilization is currently greater than 75%.

#### Warning

Disk Utilization is currently greater than 90%.

#### Alert

Disk Utilization is currently greater than 90%.

