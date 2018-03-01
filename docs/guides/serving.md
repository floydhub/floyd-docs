Floyd run command has a [serve mode](../commands/run.md#serve). After the syncronization step (where the content of your local project folder is uploaded to the Job), the remote instance will run the `python app.py` command to start a Flask web server which provide a servable API. In order to serve your model, the user require an `app.py` file which handles the incoming request and execute all the steps to evaluate the model on the processed data.

!!! important
	Note that this feature is in *preview mode* and *is not production ready* yet.
	Contact us at [support@floydhub.com](mailto:support@floydhub.com) for production ready serving support (in closed beta).

!!! important
	Before serving your model through REST API, you need to create a [floyd_requirements.txt](../commands/run.md##floyd_requirementstxt) and declare the flask requirement in it.


Here's the skeleton/template of an `app.py` file:

```python

from flask import Flask

"""Here the code to import all the dependencies you need to
load the model, data preprocess and sanity check
"""
app = Flask(__name__)
MODEL_PATH = ... # Path to the model to load

def load_model(MODEL_PATH):
	"""Load the model, you can also choose to load different model at runtime"""
	# CODE

def data_preprocessing(data):
	"""Process the data to fit into the model"""
	# CODE

# Every POST requests that will hit the end point will run `evaluate`
# The request method is POST (this method enabling us to send arbitrary data to the endpoint, including images, JSON, encoded-data, etc.)
@app.route('/<path:path>', methods=["POST"])
def evaluate(path):
	""""Preprocessing the data and evaluate the model""""
	# Sanity check
    if flask.request.method == "POST":
    	# CODE FOR DATA PREPROCESSING
    	data_preprocessing(data)
    	# CODE FOR EVALUATION
    	# RETURN THE PREDICTION

# Load the model and run the server
if __name__ == "__main__":
    print(("* Loading model and starting Flask server..."
        "please wait until server has fully started"))
    load_model()
    app.run(host='0.0.0.0')
```

## Example: Style Transfer Example

We will use a pre-trained Style Transfered model to show you how to serve your model. At the end you will be able to send any image to this API as a HTTPs request and it will be returned the style transfered image.

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

As mentioned before, for serving it is required the `app.py` file. You can see the
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
