# Insights

Insights offer warning alerts about the condition of your FloydHub machine during an active Workspace session. Specifically, Insights are connected to the available System Metrics for your Workspace. For more information on System Metrics, please visit the [System Metrics](https://docs.floydhub.com/guides/jobs/metrics/#system-metrics) docs page.

Insights will be found in the bottom bar of your Workspace, indicated by a circle icon next to the name of the System Metric.

// <TODO PROVIDE SCREEN SHOT>

There are three levels of Insight:
* Warning

// TODO Screen shot

* Danger

// TODO Screen shot

* Emergency

// TODO Screen shot

!!! important "Beta feature"
    Insights is currently in beta and under active development. If you have feedback or feature requests, please let us know - via the chat bubble or email [support@floydhub.com](mailto:support@floydhub.com)

### GPU Utilization

Insights for GPU Utilization will let you know if you're under-utilizing your GPU during your Workspace session. As a result, you might want to optimize your training code to better utilize your GPU. For example, <TODO: provide example>...

Alternatively, if you're still in active development, you might want to restart your workspace in CPU mode, and then only switch back to GPU when you're ready for the additional compute power.

#### Warning

GPU Utilization has been under 70% of capacity for the last five (5) minutes.

#### Danger

GPU Utilization has been under 70% of capacity for the last fifteen (15) minutes.

#### Emergency

GPU Utilization has been under 80% of capacity for the last thirty (30) minutes.

### RAM (Memory) Utilization

Insights for RAM Utilization will indicate when your FloydHub's machine's RAM is getting close to its maximum, which could lead to Out-of-Memory Errors. 

When you see this Insight, you might want to try ... <TODO FILL THIS IN>

This Insight will consistently track the latest reported value of your machine's RAM.

#### Warning

RAM Utilization is currently greater than 75%.

#### Danger

RAM Utilization is currently greater than 90%.

#### Emergency

RAM Utilization is currently greater than 90%.

### Disk Utilization

Insights for Disk Utilization will indicate when your FloydHub machine is running low on disk space.

When you see this Insight, it could indicate that you've generated significant amounts of data that should be separated and broken out from your Workspace's codebase.

This insight will consistently track the latest reported value of your machine's disk space.

#### Warning

Disk Utilization is currently greater than 75%.

#### Danger

Disk Utilization is currently greater than 90%.

#### Emergency

Disk Utilization is currently greater than 90%.

