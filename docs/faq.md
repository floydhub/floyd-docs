## Running Experiments

### Why does `floyd status` return an empty list even though I have several runs in my account?

Floyd CLI uses the project directory to store the run information (similar to git). So you need 
to be in the directory where you initialized the project and you should be able to see all your 
runs. You can also use the [web dashboard](https://www.floydhub.com/experiments) to view all your 
projects in one place.

### What do I do when I get "What do you do when you get “You are over the allowed limits for this operation. Consider upgrading your account”?

Floydhub currently allows only 5 active runs per user. If you require more concurrency, contact 
us from the [pricing](https://www.floydhub.com/pricing) page.

## Billing

### What payment types do you accept?

Currently, we accept credit or debit cards, including Visa, MasterCard and American Express.

### Do you keep my credit card information?

No, we do not retain any credit card information. We use [Stripe](https://stripe.com/) to 
process payments.

### When will my credit card be charged?

You can see your billing due date in the `Usage` tab on your Floydhub dashboard.
