#### If you signed up for a paid subscription plan before November 20, 2017, please see our [Legacy Plans FAQs](/faqs/plans_legacy).

Please see here for [Billing FAQs](./billing.md)

### Which Plan is right for me?

#### Beginner Plan
If you're just getting started with deep learning, the Beginner plan is for you. It is free! You can create unlimited public projects 
and datasets, and can run 1 job at a time. It comes with 20 hours of CPU compute time per month. 

If you want to run your jobs with GPU support, you can purchase [GPU Powerups](#powerups).

#### Data Scientist Plan
The Data Scientist plan is for, well, data scientists. It offers private projects/datasets and higher levels of 
[job concurrency](#what-is-job-concurrency) and storage. As in the Beginner Plan, it comes with 20 hours of CPU compute time per month. You can also purchase [Powerups](#powerups) to add GPU compute hours to supplement your plan.

For more details on our different plans, visit our [pricing
page](https://www.floydhub.com/pricing).

### What is in the Trial plan?

All new users get a free 2 hour [GPU Powerup](#powerups) for a 14 day trial period.

Once you've signed up, take FloydHub for a spin with our [Quick Start
Guide](../getstarted/quick_start.md) or [Jupyter Notebook
Guide](../getstarted/quick_start_jupyter.md)!

### How can I run GPU jobs?

To run GPU jobs, you can purchase [GPU Powerups](#powerups) from your [Powerups Dashboard](https://www.floydhub.com/settings/powerups). 

## Compute

### What is job concurrency?

Job concurrency is the number of jobs you can run in parallel. Each plan has a limit
on the number of concurrent jobs you can run. For example, in the Beginner plan,
you can only run 1 job at a time. In the Data Scientist plan, you can run up
to 8 jobs in parallel.

Having a higher concurrency is useful when you want to parallelize your training, for
example while hyperparameter sweeping.

### What will happen to my running job when I run out of computing credits?

You job will be shutdown immediately when you run out of computing credits.

If you run long-running jobs and expect them to exceed the computing hours offered by your plan, you can purchase [Powerups](#powerups).

You can also enable auto-refresh on your Powerups to ensure your long-running jobs are never killed because you ran out of computing hours. We'll automatically refresh your selected Powerup so that your job can continue running.

## Powerups

### What are Powerups?

Powerups are addons that offer you the flexibility of purchasing compute or storage depending on your needs. 
You can buy Powerups for additional CPU or GPU computing hours, or for additional storage, from your [Powerups Dashboard](https://www.floydhub.com/settings/powerups) 

### What Powerups should I buy?

This depends on your computing needs. We offer multiple tiers of Powerups:

- **CPU vs. GPU**: Pick the instance that you need for your training. GPUs reduces training time and are expensive.
- **10 vs. 50 vs. 100 hours**: Purchase a pack that suits your computing needs. Note that the larger packs offer compute at a much cheaper rate/hour than smaller packs.
- **Auto-refresh**: You can enable auto-refresh on any pack.
- **Storage Powerups**: You can purchase storage Powerups to supplement your plan's storage limits.

If you are *just starting out* and need more computing hours than your plan offers, you can start with the *GPU10 Powerup*.

If you run *long-running jobs*, you should purchase the *GPU100 with auto-refresh enabled*, to ensure that you never run out of computing credits.

If you run *critical jobs* that are not fault-tolerant, you should purchase the *GPU+ Powerup*.

### How can I buy Powerups?

You can purchase them from your [Powerups Dashboard](https://www.floydhub.com/settings/powerups)

### Why would I enable auto-refresh?

Auto-refresh ensures your long-running jobs are never killed because you [ran out of computing hours](#what-will-happen-to-my-running-job-when-i-run-out-of-computing-credits). We'll automatically refresh your selected Powerup so that your Job can continue running.

### Can I buy a Powerup if I am in the Free Plan?

Yes!

### Do Powerups expire?

Yes. Compute Powerups are valid for 1 year from the date of purchase.

### How will my Powerups be used?

Your compute hours will be consumed in the following order:

- Hours from your subscription plan
- Hours from free credits
- Hours from Powerups

## Storage

### How much storage do I get?

Each plan comes with its own storage limit. Please see the [feature comparison
table](https://www.floydhub.com/pricing/#features) for details.

### What counts against my storage?

Storage is consumed by the datasets that you upload, your code and the data that your jobs output.

Note that you are only responsible for the data that you own. For example, if you use a public dataset in your job, you won't be charged for it.

### Can I buy more storage than my plan offers?

You can purchase Storage Powerups to increase your storage limits from your [Powerups Dashboard](https://www.floydhub.com/settings/powerups)

{!contributing.md!}
