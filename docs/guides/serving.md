You can use FloydHub to deploy your trained models as REST APIs with a single command: `floyd run --mode serve`.

The `floyd run` command has a [serve mode](../commands/run.md#serve). Executing `floyd run --mode serve` from your terminal starts a Flask web server on FloydHub's servers and returns a REST endpoint that you can query.

In order to serve your model, you need to provide an `app.py` file (Flask application) which handles the incoming request and executes all the steps necessary to evaluate the model. Below is the scaffold for the `app.py` file. You can also view a complete example [here](https://github.com/floydhub/fast-style-transfer/blob/master/app.py):

```python

from flask import Flask

"""
Import all the dependencies you need to load the model,
preprocess your request and postprocess your result
"""
app = Flask(__name__)
MODEL_PATH = ... # TODO: Insert path to the model to load

def load_model(MODEL_PATH):
	"""Load the model"""
	# TODO: INSERT CODE

def data_preprocessing(data):
	"""Preprocess the request data to transform it to a format that the model understands"""
	# TODO: INSERT CODE

# Every incoming POST request will run the `evaluate` method
# The request method is POST (this method enables your to send arbitrary data to the endpoint in the request body, including images, JSON, encoded-data, etc.)
@app.route(, methods=["POST"])
def evaluate():
	""""Preprocessing the data and evaluate the model""""
	# TODO: Sanity check

    if flask.request.method == "POST":
    	# CODE FOR DATA PREPROCESSING
    	data_preprocessing(data)

    	# TODO: CODE FOR EVALUATION
    	# TODO: RETURN THE PREDICTION

# Load the model and run the server
if __name__ == "__main__":
    print(("* Loading model and starting Flask server..."
        "please wait until server has fully started"))
    load_model()
    app.run(host='0.0.0.0')
```

## Example: Deploying a Neural Style Transfer Model

We will use a pre-trained Neural Style Transfer model to demonstrate how model serving works on FloydHub. In the end you will be able to send any image to this API as a HTTPs request and it will return the style transfered image.

### Setup

For this guide we will be using [Fast Style Transfer](https://github.com/floydhub/fast-style-transfer)
project.

```bash
$ git clone https://github.com/floydhub/fast-style-transfer
$ cd fast-style-transfer
$ floyd init fast-style-transfer
Project "fast-style-transfer" initialized in the current directory
```

### Serve Mode

As mentioned before, serving requires an `app.py` file. You can see the
[app.py](https://github.com/floydhub/fast-style-transfer/blob/master/app.py) file in the sample repository. This file handles the
incoming request (take your image), executes the code in `evaluate.py` (run the model evaluation) and returns the style-transferred output image.

```bash
$ floyd run --env tensorflow-1.5:py2 --data narenst/datasets/neural-style-transfer-pre-trained-models/1:input --mode serve
Syncing code ...

JOB NAME
-------------------------------------------
narenst/projects/fast-style-transfer/5

URL to job: https://www.floydhub.com/narenst/projects/fast-style-transfer/5
URL to service endpoint: https://www.floydlabs.com/expose/mkxjJa46aJBdwP4AEdKxfU
```

### Sending requests to the REST API

Now you can send any image file as request to this API and it will return the style transferred image.

!!! important "Use the URL in the Serving tab"
    Fixed Rest endpoint from the Serving tab on floydhub.com

    ![Fixed Serving URL](../img/serving/serving_url.png)

The fixed URL endpoint also provides a load-balancer behind it: this means that if you need to scale your endpoint horizontally, by adding more machines to satisty more parallel requests, you can simply launch new serving Jobs (*you need a Plan with job concurrency > 1*) and the balancer will route the traffic to the available machines.

!!! important "Scale horizontally"
	If you need to support more requests, you can add additional serving instances and scale horizontally.

```bash
curl -o taipei_output.jpg -F "file=@./images/taipei101.jpg" https://www.floydlabs.com/serve/narenst/projects/fast-style-transfer
```

![Muse](../img/taipei_muse.jpg)

You will see the default style ([la_muse](https://github.com/floydhub/fast-style-transfer/blob/master/examples/style/la_muse.jpg)) is applied to the input image.

### Build an interactive website upon Serving

Serving is not limited to single REST endpoint. You can build complex interactive website at its top. Here's an example.

### Interactive website example: ColorNet

For this example we will be using [ColorNet](https://github.com/floydhub/colornet-template)
project.

```bash
$ git clone https://github.com/floydhub/colornet-template
$ cd colornet-template
$ floyd init colornet-template
Project "colornet-template" initialized in the current directory
```

Now launch the Serving Job and wait a couple of seconds until the endpoint will be up and running.

```bash
floyd run --mode serve --env tensorflow-1.5
```

Open with your browser the URL specified in your Serving tab: e.g. https://www.floydlabs.com/serve/alice/projects/colornet-template. You should see a similar page on which you can upload your images to colorize:

![Interactive website colornet](../img/serving/serving_web.png)

## Serving FAQS

Here a list of Frequetly Asked Questions about FloydHub serving.

### Where can I find others serving examples?

- [Colornet Example](https://github.com/floydhub/colornet-template)
- [Style Transfer Example](../examples/style_transfer.md#model-api)
- [Deep Text Correctot Example](../examples/deep_corrector#serve-model-through-rest-api)
- [Deep Convolutional Generative Adversarial Networks Example](../examples/dcgan#serve-the-model-with-a-rest-api)

You can also check the projects of the [PyTorch collection](https://www.floydhub.com/explore/frameworks/pytorch).

### Do I have to pay for the entire duration that my serving endpoint is active?

When serving models, you will be charged for the full duration that your serving endpoint is active. So, remember to [stop your job](../guides/stop_job.md) when you are no longer using the endpoint.

### What is the maximum uptime for serving?

Any serving job has a maximum uptime of 7 days. If you want serving endpoints that are up for longer durations, contact us and we can enable it for you.

### Is there any API rate limit?

There is no explicit rate limiting. The maximum number of requests handled per second will depend on the time it takes for the inference to complete. If you need to support more requests, you can add additional serving instances and scale horizontally.
