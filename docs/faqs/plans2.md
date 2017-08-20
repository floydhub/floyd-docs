## Plans

### Which Plan is right for me?

#### Free Plan
If you're just exploring, the Free plan is for you! The plan includes 
20 hours of free CPU every month. You cannot, however, use a GPU or run multiple jobs 
in parallel.

#### Data Scientist Plan
Our Data Scientist plans offer varying levels of [job concurrency](), GPU computing hours 
and storage. You can also purchase [Powerups]() to add more compute hours to supplement your plan.

**Data Scientist Base Plan**: If you are getting started with deep learning and primarily use Jupyter Notebooks, the Base plan should work well for you. You can run 2 concurrent jobs and get 100 GB of storage included in the plan. 

**Data Scientist Plus and Pro Plans**: If you are a more advanced user, you may need more job concurrency to run multiple parallel experiments and more storage for your data. The Plus and Pro plans will serve you better. 

Please see the [feature comparison table](https://www.floydhub.com/pricing/#features) for a full list of features.

### What is in the Trial plan?

All users that sign up on FloydHub are automatically enrolled in the Free plan. Additionally, we offer 2 hours of free GPU credits to try out FloydHub. The GPU credits expire in 14 days, but you will be able to use all the features of the Free plan forever.

Take FloydHub for a pin with our [Quick Start Guide](../getstarted/quick_start.md) or [Jupyter Notebook Guide](../getstarted/quick_start_jupyter.md)!

### What is included in the Free plan?

FloydHub offers a Trial Plan for all users to try out the platform. This plan includes 2 hours of free GPU compute credits, 20 hours CPU and 10 GB storage.

The free plan comes with the following:

- 20 hours of CPU compute / month
- 10 GB free storage
- Unlimited public projects and datasets
- Concurrent jobs: You can only run one job at a time
- 6 hour job timeout: The maximum runtime of a job on the Trial Plan is 6 hours. It will automatically timeout after that

You can upgrade to the [Data Scientist Plan](https://www.floydhub.com/pricing) to overcome these limits.

### Do the plans come with preemptible or dedicated instances?

The GPU and CPU compute hours included in your plan (Free or Data Scientist) are 
[preemptible instances](#preemptible-instances). This means that there is a small chance that your job will be terminated without notice. In practice, this happens infrequently and this is perfect for most users. If you need [dedicated instances](#dedicated-instances) for your jobs, you 
need to buy the GPU+ or CPU+ Powerups.

### What happened to the old Pay-as-you-go Individual Plan?

We are transitioning from the Individual Plan, which offered a pay-as-you-go payment method, to our current pricing plan. The Individual Plan is no longer available. 

### I am in the Pay-as-you-go Individual Plan. What will happen to me?

If you signed up for the Individual Plan before August 20th 2017, you will be grandfathered till October 1st 2017. After this, you will be downgraded to the 
Free plan. We will be reaching out to you with more information about this transition.

### Will my free credits expire?

The current Trial plan includes 2 hours of free GPU credits. These will expire 14 days from the day you sign up. After 14 days, you will be transitioned to our Free plan.

### Are there any academic discounts for students?

We don't have discounts. A lot of students create content for us. TODO
If you are willing to create content for us, we will give you *free GPU credits* in exchange! 

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

### Preemptible Instances

#### What is the difference between GPU and GPU+?

GPU and CPU are preemptible instances. GPU+ and CPU+ are dedicated instances.

Jobs run on premptible instances (GPU or CPU) can be terminated (preempted ) by FloydHub if 
it requires access to those resources for other, higher priority tasks. Jobs run on 
dedicated instances (GPU+ or CPU+) will never be terminated.

#### Why do you use preemptible instances?

To be able to offer you compute at a much lower cost.

We have a fixed pool of resources that we have to allocate amongst all our users. Some of our users require dedicated instances and are willing to pay the premium for uninterrupted access. But, the majority of our users can tolerate a 98% job uptime SLA for the significant price savings that preemptible instances offer.

#### What is the SLA of Preemptible instances and Dedicated instances?

Preemptible instances have 98% job up time SLA. This means that there is a &lt;2% chance 
that your job will be terminated at any point during its runtime.

Dedicated instances have 99.95% job up time SLA.

#### When should I use Dedicated instances?

If your job is not fault tolerant and cannot withstand a small (&lt;2%) chance 
of your job being shutdown without notice, you should use our `"+"` Dedicated instances. 
Price sensitivity also plays a factor - dedicated instances are more expensive than 
premptible instances.

Given that deep learning models typically train over long periods of time, it 
is good practice to build your application to be fault tolerant by regularly checkpointing your training.

#### Will I get a refund if my job is preempted?

No. 

Our preemptible instances have a 98% job uptime SLA. By using them, you are accepting a small chance 
of your job being terminated without notice, in exchange for paying a much lower price than dedicated instances.


### What will happen to my running job when I run out of computing credits?




## Powerups

### What are Powerups?

Powerups are similar to prepaid cards that you can buy to add additional data or 
talk-time for your phone.

Your subscription plan comes with a monthly quota of CPU and GPU computing hours. 
If you need more computing hours, you can buy Powerups to supplement your plan.

### What Powerups should I buy?

If you are a 

### Can I buy a Powerup if I am in the Free Plan?

No. You have to be enrolled in one of the Data Scientist plans to be eligible for 
purchasing Powerups.

### Do Powerups expire?

Yes. Powerups are valid for 1 year from the date of purchase.

### How can I ensure that my jobs are not killed because I run out of computing credits?

If your job's runtime exceeds the compute credits you have available, it will be killed. 
See this [FAQ]() for details.

To ensure your jobs run uninterrupted, you can enable auto-refresh on your Powerups.


## Storage

### How much storage do I get?

Each plan comes with its own storage limit. For example, the Free plan has 
10GB storage, while the Data Scientist Pro plan has 400GB. Please see the 
[feature comparison table]() for details.

### Can I buy more storage than my plan offers?

The Data Scientist Pro plan includes 400GB of storage. If this doesn't fit your needs, 
please contact us at [support@floydhub.com](mailto:support@floydhub.com).

We will soon have a storage Powerup that can you buy to add more storage to your base plan. 


## Billing

### What forms of payments do you accept?

We accept Visa, MasterCard, American Express and Discover credit and debit cards. We do not accept prepaid cards at the moment. 

We are a US based company. If you are outside the US, please ensure your card has 
international transactions enabled.

### How am I billed?

### Can I upgrade or downgrade my plan?

You can upgrade, downgrade or cancel your paid subscriptions at anytime from your [Plans page]() under Settings on your dashboard.

When you upgrade, you will be immediately elevated to the new plan. When you downgrade, your new plan will start at the end of your billing cycle (since you will have already paid for the month in advance).

Upgrades and downgrades inside the Data Scientist plans do not affect any Powerups you 
may have purchased.

### Do you offer refunds?

No, we do not offer refunds. If there are extenuating circumstances, please open a ticket by contacting our support team.