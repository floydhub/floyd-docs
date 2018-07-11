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
@app.route('/<path:path>', methods=["POST"])
def evaluate(path):
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

!!! important
	Before serving your model, you need to create a [floyd_requirements.txt](../commands/run.md#floyd_requirementstxt) and add `flask` as a requirement in it.

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

### Where can I find others serving examples?

- [Style Transfer Example](../examples/style_transfer.md#model-api)
- [Deep Text Correctot Example](../examples/deep_corrector#serve-model-through-rest-api)
- [Deep Convolutional Generative Adversarial Networks Example](../examples/dcgan#serve-the-model-with-a-rest-api)

You can also check the projects of the [PyTorch collection](https://www.floydhub.com/explore/frameworks/pytorch).

### Do I have to pay for the entire duration that my serving endpoint is active?

When serving models, you will be charged for the full duration that your serving endpoint is active. So, remember to [stop your job](../guides/stop_job.md) when you are no longer using the endpoint. 

Serving is currently a beta feature. In the near future we will be able to charge users per API call.

### What is the maximum uptime for serving?

Any serving jobs has a maximum uptime of 7 days. The 7 day timeout is common across all jobs you run on FloydHub, whether it be Jupyter notebooks, command jobs, or serve jobs.

### Is there any API rate limit?

There is no limit, but the Flask web server can handle only 1 request at a time. This mean that it will block all other requests during that time.
