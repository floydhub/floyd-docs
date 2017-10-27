Please see here for [Billing FAQs](./billing.md)

## Plans

### Which Plan is right for me?

#### Free Plan
If you're just exploring, the Free plan is for you! You are automatically
enrolled in the Free plan when you sign up on FloydHub. It includes 20 hours of
free CPU every month. You cannot, however, use a GPU or run multiple jobs in
parallel.

#### Data Scientist Plan
Our Data Scientist plans offer varying levels of [job concurrency](#what-is-job-concurrency), GPU computing hours
and storage. You can also purchase [Powerups](#powerups) to add more compute hours to supplement your plan.

For more details on our different plans, visit our [pricing
page](https://www.floydhub.com/pricing). Please see the [feature comparison
table](https://www.floydhub.com/pricing/#features) for a full list of each
plan's features.

### What is in the Trial plan?

All users that sign up on FloydHub are automatically enrolled in the Free plan.
Refer to our [pricing page](https://www.floydhub.com/pricing/#features) for
details on the Free plan.


Once you've signed up, take FloydHub for a spin with our [Quick Start
Guide](../getstarted/quick_start.md) or [Jupyter Notebook
Guide](../getstarted/quick_start_jupyter.md)!

### Do the plans come with preemptible or dedicated instances?

The GPU and CPU compute hours included in your plan (Free or Data Scientist) are
[preemptible instances](#preemptible-instances). This means that there is a small chance that your job will be terminated without notice. In practice, this happens infrequently and this is perfect for most users. If you need [dedicated instances](#dedicated-instances) for your jobs, you
can buy the GPU+ or CPU+ Powerups.

### Do my remaining compute credits roll over each month if I don't use them all?

No, your monthly Plan compute credits are not rolled over. However, your Powerup credits will remain valid for one year from purchase date.

### What happened to the old Pay-as-you-go Individual Plan?

We are transitioning from the Individual Plan, which offered a pay-as-you-go payment method, to our current pricing plan. The Individual Plan is no longer available for new users.

### I am in the Pay-as-you-go Individual Plan. What will happen to me?

If you signed up for the Individual Plan before August 20th 2017, you will be grandfathered till October 1st 2017. After this, you will be automatically enrolled in the Free plan. Please note that any remaining promotional credits will also expire on this date.

Please [upgrade](https://www.floydhub.com/settings/plan) to one of the Data Scientist plans to continue using FloydHub without interruption. We will also be reaching out to you with more information about this transition.

### Why did I not get 100 free GPU hours when I signed up?

We offered 100 hours of free GPU for all users during our promotional period. This has ended.

### Are there any academic discounts for students?

We don't have discounts. However, a lot of students create content for us. If you are willing to contribute high quality content to FLoydHub, we will give you *free GPU credits* in exchange!

Content we are looking for:

- Technical blogs on deep learning and AI
- FloydHub tutorials, text or video
- Port popular deep learning projects to FloydHub
- Create interesting datasets
- &lt;Insert your own idea here&gt;

If this is interesting to you, please let us know about it [here](https://docs.google.com/forms/d/1dBA_KJ0_su8m8O2ij3dqF7aI3-EK89zjzxA0k-y8FdM/viewform?edit_requested=true).

## Compute

### What is job concurrency?

Job concurrency is the number of jobs you can run in parallel. Each plan has a limit
on the number of concurrent jobs you can run. For example, in the Free plan,
you can only run 1 job at a time. In the Data Scientist Pro plan, you can run up
to 8 jobs in parallel.

Having a higher concurrency is useful when you want to parallelize your training, for
example while hyperparameter sweeping.

### What will happen to my running job when I run out of computing credits?

You job will be shutdown immediately when you run out of computing credits.

If you run long-running jobs and expect them to exceed the computing hours offered by your plan, you can purchase [Powerups](#powerups).

You can also enable auto-refresh on your Powerups to ensure your long-running jobs are never killed because you ran out of computing hours. We'll automatically refresh your selected Powerup so that your job can continue running.

### Preemptible vs. Dedicated Instances

#### Preemptible Instances

Preemptible instances have medium job uptime SLA of 98%. This means that there is a small chance that your job can be terminated (preempted) at any point during its runtime by FloydHub if it requires access to those resources for other, higher priority tasks.

Preemptible instances (CPU / GPU) offer top notch compute at affordable prices, in exchange for fault tolerance.

Note that SLA refers to what we can guarantee. In practice, this happens infrequently. Historically, less than 0.1% of jobs run on FloydHub have encountered interruption. However, you need to be aware that there is the possibility.

##### Why Do You Use Preemptible Instances?

To be able to offer you compute at a much lower cost.

We have a fixed pool of resources that we have to allocate amongst all our users. Some of our users require dedicated instances and are willing to pay the premium for uninterrupted access. But, the majority of our users can tolerate a 98% job uptime SLA for the significant price savings that preemptible instances offer.

##### Will I Get a Refund if My Job is Preempted?

No.

Our preemptible instances have a 98% job uptime SLA. By using them, you are
accepting a small chance of your job being terminated without notice, in
exchange for paying a much lower price than dedicated instances.

##### How Will I Know When My Job Is Preempted?

Your job's state will turn from `Running` to `Shutdown`. We will send you a
notification informing you about this. Unfortunately, we are currently unable
to warn your ahead of time of an impending preemption.

##### What is the SLA of Preemptible Instances?

Preemptible instances have 98% job up time SLA.

#### Dedicated Instances

Dedicated instances have high job uptime SLA of 99.95%. Use dedicated instances for your jobs if they are critical or not fault tolerant. You can purchase '+' [Powerups](#powerups) (CPU+ / GPU+) to utilize dedicated instances.

##### Why Do You Use Dedicated Instances?

If your job is not fault tolerant and cannot withstand a small (&lt;2%) chance
of your job being shutdown without notice, you should use our `"+"` Dedicated instances.

Price sensitivity also plays a factor - dedicated instances are more expensive
than premptible instances.

Given that deep learning models typically train over long periods of time, it
is good practice to build your application to be fault tolerant by regularly checkpointing your training.

##### What is the SLA of Dedicated instances?

Dedicated instances have 99.95% job up time SLA.

### What is the difference between GPU vs. GPU+ and CPU vs. CPU+?

GPU and CPU are [preemptible instances](#preemptible-instances). GPU+ and CPU+ are [dedicated instances](#dedicated-instances).

## Powerups

### What are Powerups?

Your subscription plan comes with a monthly quota of CPU and GPU computing hours.
If you need more computing hours, you can buy Powerups to supplement your plan.

### What Powerups should I buy?

This depends on your computing needs. We offer multiple tiers of Powerups:

- **Preemptible vs. Dedicated**: CPU / GPU are affordable [preemptible instances](#preemptible-instances), CPU+ / GPU+ are high-reliability [dedicated instances](#dedicated-instances).
- **10 vs. 50 vs. 100 hours**: Purchase a pack that suits your computing needs. Note that the larger packs offer compute at a much cheaper rate/hour than smaller packs.
- **Auto-refresh**: You can enable auto-refresh on any pack.

If you are *just starting out* and need more computing hours than your plan offers, you can start with the *GPU10 Powerup*.

If you run *long-running jobs*, you should purchase the *GPU100 with auto-refresh enabled*, to ensure that you never run out of computing credits.

If you run *critical jobs* that are not fault-tolerant, you should purchase the *GPU+ Powerup*.

### How can I buy Powerups?

You can purchase them from your [Powerups Dashboard](https://www.floydhub.com/settings/powerups)

### Why would I enable auto-refresh?

Auto-refresh ensures your long-running jobs are never killed because you [ran out of computing hours](#what-will-happen-to-my-running-job-when-i-run-out-of-computing-credits). We'll automatically refresh your selected Powerup so that your Job can continue running.

### Can I buy a Powerup if I am in the Free Plan?

No. You have to be enrolled in one of the Data Scientist plans to be eligible for
purchasing Powerups.

### Do Powerups expire?

Yes. Powerups are valid for 1 year from the date of purchase.

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

If our Data Scientist Pro plan's storage doesn't meet your needs, please
contact us at [support@floydhub.com](mailto:support@floydhub.com).

We will soon have a storage Powerup that can you buy to add more storage to your base plan.

{!contributing.md!}
