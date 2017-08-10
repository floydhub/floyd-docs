### What payment types do you accept?

Currently, we accept credit or debit cards, including Visa, MasterCard and American Express.

### Do you keep my credit card information?

No, we do not retain any credit card information. We use
[Stripe](https://stripe.com/) to process payments.

### When will my credit card be charged?

You can see your billing due date in the [Usage](https://dev.floydhub.com/settings/billing/) tab on your Floydhub settings.

### What will I be charged for?

You are charged for your compute (CPU/GPU) usage and storage.

- **Compute**: You will be charged exactly for the duration that your job runs, rounded off to the nearest second. You will be charged our [current rates](https://www.floydhub.com/pricing) for CPU or GPU, depending on the compute instance your job runs in.

    Note that you are only charged for compute when your job is in the *Running* state. You will *not* be charged when your job is in any other state, including *Queued* and *Shutdown*.

- **Storage**: You will also be charged for the storage you consume, rounded off to the nearest kB. You will be charged for the duration of your storage per our [current rates](https://www.floydhub.com/pricing).

    Storage is consumed by the datasets that you upload, your code and the data that your jobs output.

{!contributing.md!}
