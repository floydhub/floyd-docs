# Creating a 'Run on FloydHub' Button

The 'Run on FloydHub' button enables users to run CPU or GPU-powered workspaces on FloydHub with little or no configuration. The button is ideal for sharing open-source projects, reproducing academic research papers, teaching educational courses to students, and anywhere else you want people to be able to quickly run and reproduce your projects.

The button is well-suited for use in README files, and is intended to serve as a replacement for the manual configuration of your environment, code, and data required to reproduce your work.

Here's an example button that trains a sentiment analysis TensorFlow model on FloydHub (including attaching the required datasets). You can try it out now by clicking this button:

[![Run](https://static.floydhub.com/button/button-small.svg)](https://floydhub.com/run?template=https://github.com/floydhub/sentiment-analysis-template)

If you'd like to add something like this to your own projects, then this is the guide for you. This document describes how to add the 'Run on FloydHub' button snippet to your README, and how to use these buttons to make it easy to run, reproduce, and share your code on FloydHub workspace.


## Adding the FloydHub button

The only thing that the button snippet needs to know is the location of your public repo on GitHub. There are two ways of referencing your repository, which we're going to call a `template`:

* **Basic Setup** This is the preferred approach. Add the button code without specifying the URL of your repository. This is best for GitHub-hosted documentation on your project's README. If you don't specify a `template` parameter, FloydHub infers it from the location of the button using the `referrer` header. This makes the button stable under forks of the repository.

* **Advanced Setup**: Using an explicit `template` query parameter that points to the repo. This is useful for buttons sitting outside of GitHub, such as in blog posts or documentation (like this page!)


### Basic Setup

If you're embedding the button in a GitHub repository's README file, FloydHub will automatically infer the repository URL from the `referrer` header when someone clicks the button.

!!! important "Using an implicit template"
    This is convenient because it avoids hard-coding the specific repository URL into the button, allowing forks of the repository to work properly without a change to the button href.

Here's an example that you can copy and paste directly into your own project's README file:

```markdown
[![Run on FloydHub](https://static.floydhub.com/button/button-small.svg)](https://floydhub.com/run)
```

Here's the equivalent content as HTML:

```html
<a href="https://floydhub.com/run">
    <img src="https://static.floydhub.com/button/button-small.svg" alt="Run">
</a>
```

If you paste one of these snippets into your repo, then anyone will able to click that button and open your code in a live Workspace on FloydHub.

### Advanced Setup

Again, this approach is for when you want to add a Run on FloydHub somewhere else, other than GitHub.

Use the following Markdown snippet as a template, changing the `template` query parameter to the URL of your repository:

```markdown
[![Run on FloydHub](https://static.floydhub.com/button/button-small.svg)](https://floydhub.com/run?template=https://github.com/floydhub/sentiment-analysis-template)
```

Here's the equivalent content as HTML:

```html
<a href="https://floydhub.com/run?template=https://github.com/floydhub/sentiment-analysis-template">
    <img src="https://static.floydhub.com/button/button-small.svg" alt="Run">
</a>
```

That's it. Now FloydHub will always know the location of your code, even if you decide to put this button somewhere else, like a blog post or your own website.

## Using a floyd.yml config file to improve reproducibility

Sometimes you'll want to be more specific about how the Workspace is configured when someone reproduces your work. For example, you might want to ensure that people run your code in GPU mode, or use a specific environment like PyTorch 0.4, or attach specific datasets to the Workspace. 

In this case, you should add a `floyd.yml` file to your repo.

`floyd.yml` is a configuration file describing your FloydHub deep learning environment. It declares your machine type, deep learning framework (e.g. TensorFlow, PyTorch), attached datasets, and other information for running jobs and workspaces on FloydHub.

There are no specific tools required to create a `floyd.yml` for your project. The `floyd.yml` schema has only two required fields: `env` and `machine`.

Here's a sample `floyd.yml` file:

```yml
env: tensorflow-1.8
machine: gpu
```

If your app requires any datasets, those can be specified in the `floyd.yml`:

```yml
env: tensorflow-1.7
machine: cpu
data:
  - source: floydhub/datasets/imdb-preprocessed/1
    destination: imdb
```

For more information, view the [floyd.yml schema documentation](../floyd_config.md)


#### Testing the floyd.yml file

Now that you've created a `floyd.yml` file for your project and added it to the project's repo on GitHub, you can easily test that it is valid and that your project can be successfully created. Use your web browser to visit:

```
https://floydhub.com/run?template=https://github.com/<your_username>/<your_repo_name>
```

If this was successful, then you should be able to automatically create a new project along with a Workspace that contains your repo's code.

## Button image

You can access the link to the large 'Run on FloydHub' button image (as a SVG file) here:

```
https://static.floydhub.com/button/button.svg
```

![large button](https://static.floydhub.com/button/button.svg)

The small version is available here (also as an SVG). You can use either one.

```
https://static.floydhub.com/button/button-small.svg
```

![small button](https://static.floydhub.com/button/button-small.svg)


## FAQ

### Does this work with private repos?

No, not right now. We are planning to add support for running for private repos.

### Does this work with branches?

No, not right now. We are planning to add support for running from branches.

### Does this only work with repos on GitHub?

Yes.

### Where can I ask more questions or provide feedback on the Run on FloydHub button?

We'd love to hear your questions and feedback on the Run on FloydHub button, so please [send us an email](mailto:support@floydhub.com).