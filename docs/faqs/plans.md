### What is in the Trial Plan?

FloydHub offers a Trial Plan for users to try out the platform. This plan includes 2 hours of free GPU compute credits (or 20 hours of CPU compute). Please refer to our [Quick Start Guide](../getstarted/quick_start.md) or [Jupyter Notebook Guide](../getstarted/quick_start_jupyter.md) to try Floyd out!

The free plan comes with the follow limits:

- 1 concurrent job: This means that you can only run one job at a time
- 1 hour job timeout: The maximum runtime of a job on the Trial Plan is 1 hour. It will automatically timeout after that

You can upgrade to the [Paid Plan](https://www.floydhub.com/pricing) to overcome these limits.


### Why did I not get 100 free GPU hours when I signed up?

We offered 100 hours of free GPU for all users during our promotional period. This has ended. 

In our current Trial Plan, all users get 2 hours of free GPU or 20 hours of CPU compute time for running your projects. We hope this will give you enough time to evaluate Floydhub for your needs. We are working on a new free plan right now to better help new users explore the platform.


### Is there a student discount?

Not at the moment, but we are currently working out a Student Plan. We will
post the details very soon :)

### Payment processing failed. Whay am I unable to add my payment method?

When you upgrade from the Trial plan to a Paid plan, you will be prompted to enter your payment information. When you enter your details, you may received a "Error: Payment processing failed" error notification.

![Payment processing failed](../img/payment-processing-failed.jpg)

Some common causes are:

- **Credit and Debit cards only**: We currently accept only Visa and Mastercard credit and debit cards. Since our billing is based on usage and is recurring, we do not accept prepaid cards. Please ensure you are using a valid credit or debit card.
- **Balance**: We issue a small $0-1 transaction on your card as a pending authorization request between our billing system and the bank that issued your credit or debit card. If this authorization fails, you won't be able to add your card. Please ensure you have enough balance and are using a valid card. *Note*: This is an authorization request only, not an actual charge.
- **Fraud Detection**: We use Stripe for managing all our payments. They have their own fraud detection algorithm which can decline some cards. Please try a different payment method.

If you are still unable to add your payment, please contact us directly at support@floydhub.com.