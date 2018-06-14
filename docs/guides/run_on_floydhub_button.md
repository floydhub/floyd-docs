# Creating a 'Run on FloydHub' Button

The 'Run on FloydHub' button enables users to run CPU or GPU-powered workspaces on FloydHub with little or no configuration. The button is ideal for sharing open-source projects, reproducing academic research papers, teaching educational courses to students, and anywhere else you want people to be able to quickly run and reproduce your projects.

The button is well-suited for use in README files, and is intended to serve as a replacement the manual configuration of your environment, code, and data required to reproduce your work.

Here's an example button that trains a sentiment analysis TensorFlow model on FloydHub (including attaching the required datasets):

[![Run](https://s3-us-west-2.amazonaws.com/floydhub-assets/button/button.png)](https://floydhub.com/run?template=https://github.com/floydhub/sentiment-analysis-template)

This document describes the requirements for using the 'Run on FloydHub' button, and how to use these buttons to make it easy to run, reproduce, and share your projects on FloydHub.


## Requirements

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

For more information, view the floyd.yml schema documentation.


## Testing the floyd.yml file

Now that you've created a `floyd.yml` file for your project and added it to the project's repo on GitHub, you can easily test that it is valid and that your project can be successfully created. Use your web browser to visit:

```
https://floydhub.com/run?template=https://github.com/<your_username>/<your_repo_name>
```

If this was successful, then you should be able to automatically create a new project along with a Workspace that contains your repo's code.


## Adding the FloydHub button

Once you've verified that your `floyd.yml` file is valid and working as expected, it's time to add a button to your repo README.

There are two ways of referencing the template source code repository:

* Resolve template implicitly. This is best for GitHub-hosted documentation on your project's README. If you don't specific a `template` parameter, FloydHub infers it from the location of the button using the `referrer` header. This makes the button stable under forks of the repository.

* Using an explicit `template` query paramter that points to the repo. This is useful for buttons sitting outside of GitHub, such as in blog posts or documentation (like this!)


### Using an implicit template

If you're embedding the button in a GitHub repository's README file, FloydHub will automatically infer the repository URL from the `referrer` header when someone clicks the button.

!!! important "Using an implicit template"
    This is convenient because it avoids hard-coding the specific repository URL into the button, allowing forks of the repository to work properly without a change to the button href.

Here's an example.

```markdown
[![Run on FloydHub](https://s3-us-west-2.amazonaws.com/floydhub-assets/button/button.png)](https://floydhub.com/run)
```

Here's the equivalent content as HTML:

```html
<a href="https://floydhub.com/run">
    <img src="https://s3-us-west-2.amazonaws.com/floydhub-assets/button/button.png" alt="Run">
</a>
```

### Adding an explicit parameter

Use the following Markdown snippet as a template, changing the `template` query paramter to the URL of your repository:

```markdown
[![Run on FloydHub](https://s3-us-west-2.amazonaws.com/floydhub-assets/button/button.png)](https://floydhub.com/run?template=https://github.com/floydhub/sentiment-analysis-template)
```

Here's the equivalent content as HTML:

```html
<a href="https://floydhub.com/run?template=https://github.com/floydhub/sentiment-analysis-template">
    <img src="https://s3-us-west-2.amazonaws.com/floydhub-assets/button/button.png" alt="Run">
</a>
```

### Button image

You can access the link to the 'Run on FloydHub' button image (as a PNG file) here:

```
https://s3-us-west-2.amazonaws.com/floydhub-assets/button/button.png
```


## FAQ

### Does this work with private repos?

No, not right now. We are planning to add support for running form private repos.

### Does this work with branches?

No, not right now. We are planning to add support for running from branches.

### Does this only work with repos on GitHub?

Yes.

### Where can I ask more questions or provide feedback on the Run on FloydHub button?

We'd love to hear your questions and feedback on the Run on FloydHub button, so please [send us an email]((mailto:support@floydhub.com)).