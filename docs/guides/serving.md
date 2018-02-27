Floyd run command has a [serve mode](../commands/run.md#serve). This will upload the files in the current directory and run a special command - `python app.py`. This file handles the incoming request, executes the logic and returns the output. Floyd expects this file to contain the code to run a web server(based on Flask).

!!! IMPORTANT
	Note that this feature is in *preview mode* and *is not production ready* yet.
	Contact us at [support@floydhub.com](mailto:support@floydhub.com) for production ready serving support (in closed beta).

!!! important
	Before serving your model through REST API, you need to create a [floyd_requirements.txt](../commands/run.md##floyd_requirementstxt) and declare the flask requirement in it.

## Example: Style Transfer Example

After you have trained the model following the [Style Transfer Example](../examples/style_transfer.md), you can host the model as a REST API. This means you can send any image to this API as a HTTPs request and it will be style transferred.

### Serve Mode

You can see the
[app.py](https://github.com/floydhub/fast-style-transfer/blob/master/app.py) file in the sample repository. This file handles the
incoming request(take your images), executes the code in `evaluate.py`(run the model evaluation) and returns the styled output.

```bash
$ floyd run --env tensorflow-0.12:py2 --data narenst/datasets/neural-style-transfer-pre-trained-models/1:input --mode serve
Syncing code ...

JOB NAME
-------------------------------------------
narenst/projects/fast-style-transfer/5

URL to job: https://www.floydhub.com/narenst/projects/fast-style-transfer/5
URL to service endpoint: https://www.floydlabs.com/expose/mkxjJa46aJBdwP4AEdKxfU
```

### Sending requests to the REST API

Now you can send any image file as request to this API and it will return the style transferred image.

```bash
curl -o taipei_output.jpg -F "file=@./images/taipei101.jpg" https://www.floydlabs.com/expose/mkxjJa46aJBdwP4AEdKxfU
```

![Jupyter](../img/taipei_muse.jpg)

You will see the default style ([la_muse](https://github.com/floydhub/fast-style-transfer/blob/master/examples/style/la_muse.jpg)) is applied to the input image.

## Serving FAQS

Here a list of Frequetly Asked Questions about FloydHub serving.

### Where can I find others serving example?

All the Examples provide the serve feature section:

- [Style Transfer Example](../examples/style_transfer.md#model-api)
- [Deep Text Correctot Example](../examples/deep_corrector#serve-model-through-rest-api)
- [Deep Convolutional Generative Adversarial Networks Example](../examples/dcgan#serve-the-model-with-a-rest-api)

You can also check the projects of the [PyTorch collection](https://www.floydhub.com/explore/frameworks/pytorch).

### Have I to pay for the entire time that the instance is running?

When serving models, you will be charged for the full duration your service is up. Serving is only a beta feature now. But we have planned different improvement in our roadmap such as charging users based on the number of API calls.

### What is the maximum uptime for serving?

In preview mode the API has a maximum uptime of 7 days. The 7 day timeout is common across all the instances you start on FloydHub - may it be Jupyter notebooks, command jobs or serve jobs. We are planning to remove this constraint in the next version.

### Is there any API rate limit?

There isn't a limit, but the Flask web server can handle only 1 request at a time. This mean that it will block all other requests during that time.
