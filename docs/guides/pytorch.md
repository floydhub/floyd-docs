# PyTorch

![PyTorch Logo](https://upload.wikimedia.org/wikipedia/commons/9/96/Pytorch_logo.png)

Below is the list of python packages already installed with the PyTorch environments. Don't worry if the package you are looking for is missing, you can easily install extra-dependencies by following [this guide](jobs/installing_dependencies.md).

!!! important

    Installing a different `PyTorch` version from the one provided by the environment can break the existing environment and cause reproducibility issue. Be careful!

!!! warning

	Some packages may have different version according to the machine selected. 

## PyTorch-1.5

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v10.2.89 | CuDNN 7.6.5
GPU2 | Cuda v10.2.89 | CuDNN 7.6.5

Python packages:

```bash
absl-py==0.9.0
annoy==1.16.3
appdirs==1.4.4
args==0.1.0
astunparse==1.6.3
atari-py==0.2.6
attrs==19.3.0
backcall==0.1.0
beautifulsoup4==4.9.0
bleach==3.1.5
blis==0.4.1
Bottleneck==1.3.2
box2d-py==2.3.8
cachetools==4.1.0
catalogue==1.0.0
certifi==2020.4.5.1
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==1.3.0
cupy==7.4.0
cupy-cuda102==7.4.0  (GPU machines)
cycler==0.10.0
cymem==2.0.3
Cython==0.29.17
cytoolz==0.10.1
decorator==4.4.2
defusedxml==0.6.0
distlib==0.3.0
dlib==19.19.0
entrypoints==0.3
fastai==1.0.61
fastprogress==0.2.3
fastrlock==0.4  (GPU machines)
filelock==3.0.12
Flask==1.1.2
floyd-cli==0.11.17
funcsigs==1.0.2
future==0.18.2
gast==0.3.3
google-auth==1.14.3
google-auth-oauthlib==0.4.1
google-pasta==0.2.0
grpcio==1.28.1
gym==0.17.2
gym-retro==0.8.0
h5py==2.10.0
idna==2.9
imagecodecs==2020.2.18
imageio==2.8.0
importlib-metadata==1.6.0
incremental==17.5.0
ipykernel==5.2.1
ipython==7.14.0
ipython-genutils==0.2.0
ipywidgets==7.5.1
itsdangerous==1.1.0
jedi==0.17.0
jellyfish==0.7.2
Jinja2==2.11.2
joblib==0.14.1
json5==0.9.4
jsonschema==3.2.0
jupyter==1.0.0
jupyter-client==6.1.3
jupyter-console==6.1.0
jupyter-core==4.6.3
jupyterlab==2.1.2
jupyterlab-server==1.1.3
kaggle==1.5.6
Keras @ git+git://github.com/fchollet/keras.git@f295e8ee39d4ba841ac281a9337d69c7bc5e0eb6
Keras-Applications==1.0.8
Keras-Preprocessing==1.1.0
kiwisolver==1.2.0
Markdown==3.2.2
MarkupSafe==1.1.1
marshmallow==2.21.0
matplotlib==3.2.1
menpo==0.10.0
mistune==0.8.4
mock==4.0.2
mpmath==1.1.0
murmurhash==1.0.2
nbconvert==5.6.1
nbformat==5.0.6
networkx==2.4
nltk==3.5
notebook==6.0.3
numexpr==2.7.1
numpy==1.18.4
nvidia-ml-py3==7.352.0
oauthlib==3.1.0
opencv-contrib-python==4.2.0.34
opencv-python==4.2.0.34
opt-einsum==3.2.1
packaging==20.3
pandas==1.0.3
pandocfilters==1.4.2
parso==0.7.0
path==13.1.0
path.py==12.4.0
pathlib2==2.3.5
pbr==5.4.5
pexpect==4.8.0
pickleshare==0.7.5
Pillow==7.1.2
plac==1.1.3
plotly==4.7.1
pooch==1.1.0
preshed==3.0.2
prometheus-client==0.7.1
prompt-toolkit==3.0.5
protobuf==3.11.3
ptyprocess==0.6.0
pyasn1==0.4.8
pyasn1-modules==0.2.8
pydot==1.4.1
pyemd==0.5.1
pyglet==1.5.0
Pygments==2.6.1
pynvrtc==9.2
PyOpenGL==3.1.5
PyOpenGL-accelerate==3.1.5
pyparsing==2.4.7
Pyphen==0.9.5
pyrsistent==0.16.0
python-dateutil==2.8.1
python-slugify==4.0.0
pytz==2020.1
PyWavelets==1.1.1
PyYAML==5.3.1
pyzmq==19.0.1
qtconsole==4.7.3
QtPy==1.9.0
raven==6.10.0
regex==2020.5.7
requests==2.23.0
requests-oauthlib==1.3.0
requests-toolbelt==0.9.1
retrowrapper==0.3.0
retrying==1.3.3
rsa==4.0
sacremoses==0.0.43
scikit-image==0.17.1
scikit-learn==0.22.2.post1
scipy==1.4.1
seaborn==0.10.1
Send2Trash==1.5.0
sentencepiece==0.1.86
six==1.14.0
sklearn==0.0
soupsieve==2.0
spacy==2.2.4
srsly==1.0.2
sympy==1.5.1
tabulate==0.8.7
tensorboard==2.2.1
tensorboard-plugin-wit==1.6.0.post3
tensorboardX==2.0
tensorflow @ file:///tmp/pip/tensorflow-2.2.0-cp37-cp37m-linux_x86_64.whl
tensorflow-estimator==2.2.0
termcolor==1.1.0
terminado==0.8.3
testpath==0.4.4
text-unidecode==1.3
textacy==0.10.0
thinc==7.4.0
tifffile==2020.5.7
tokenizers==0.7.0
toolz==0.10.0
torch @ http://download.pytorch.org/whl/cu102/torch-1.5.0-cp37-cp37m-linux_x86_64.whl
torchtext==0.6.0
torchvision @ http://download.pytorch.org/whl/cu102/torchvision-0.6.0-cp37-cp37m-linux_x86_64.whl
tornado==6.0.4
tqdm==4.46.0
traitlets==4.3.3
transformers==2.9.0
urllib3==1.24.3
uWSGI==2.0.18
virtualenv==20.0.20
wasabi==0.6.0
wcwidth==0.1.9
webencodings==0.5.1
Werkzeug==1.0.1
widgetsnbextension==3.5.1
wrapt==1.12.1
xgboost==1.0.2
zipp==3.1.0
zmq==0.0.0
```


## PyTorch-1.4

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v10.0.130 | CuDNN 7.6.3
GPU2 | Cuda v10.0.130 | CuDNN 7.6.3

Python packages:

```bash
absl-py==0.9.0
annoy==1.16.2
args==0.1.0
astor==0.8.1
atari-py==0.2.6
attrs==19.3.0
backcall==0.1.0
beautifulsoup4==4.8.2
bleach==3.1.0
blis==0.4.1
boto3==1.11.7
botocore==1.14.7
Bottleneck==1.3.1
box2d-py==2.3.8
cachetools==3.1.1
catalogue==0.0.8
certifi==2019.11.28
cffi==1.13.2  (GPU machines)
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==1.2.2
cudf-cuda100==0.6.1  (GPU machines)
cuml-cuda100==0.6.1  (GPU machines)
cupy==7.0.0  (GPU machines)
cupy-cuda100==7.0.0  (GPU machines)
cycler==0.10.0
cymem==2.0.3
Cython==0.29.14
cytoolz==0.10.1
dataclasses==0.7
decorator==4.4.1
defusedxml==0.6.0
dlib==19.18.0
docutils==0.15.2
entrypoints==0.3
fastai==1.0.60
fastprogress==0.2.2
fastrlock==0.4  (GPU machines)
Flask==1.1.1
floyd-cli==0.11.17
funcsigs==1.0.2
future==0.18.2
gast==0.2.2
google-auth==1.10.1
google-auth-oauthlib==0.4.1
google-pasta==0.1.8
grpcio==1.26.0
gym==0.15.4
gym-retro==0.7.0
h5py==2.10.0
idna==2.8
imageio==2.6.1
importlib-metadata==1.2.0
incremental==17.5.0
ipykernel==5.1.3
ipython==7.10.1
ipython-genutils==0.2.0
ipywidgets==7.5.1
itsdangerous==1.1.0
jedi==0.15.1
jellyfish==0.7.2
Jinja2==2.10.3
jmespath==0.9.4
joblib==0.14.0
json5==0.8.5
jsonschema==3.2.0
jupyter==1.0.0
jupyter-client==5.3.4
jupyter-console==6.0.0
jupyter-core==4.6.1
jupyterlab==1.2.3
jupyterlab-server==1.0.6
kaggle==1.5.6
Keras==2.3.1
Keras-Applications==1.0.8
Keras-Preprocessing==1.1.0
kiwisolver==1.1.0
llvmlite==0.30.0  (GPU machines)
Markdown==3.1.1
MarkupSafe==1.1.1
marshmallow==2.20.5
matplotlib==3.1.2
menpo==0.9.2
mistune==0.8.4
mock==3.0.5
more-itertools==8.0.0
mpmath==1.1.0
murmurhash==1.0.2
nbconvert==5.6.1
nbformat==4.4.0
networkx==2.4
nltk==3.4.5
notebook==6.0.3
numba==0.41.0  (GPU machines)
numexpr==2.7.1
numpy==1.17.4
nvidia-ml-py3==7.352.0
nvstrings-cuda100==0.3.0.post1  (GPU machines)
oauthlib==3.1.0
opencv-contrib-python==3.4.0.12
opencv-python==4.1.2.30
opt-einsum==3.1.0
packaging==20.0
pandas==0.25.3
pandocfilters==1.4.2
parso==0.5.1
path==13.1.0
path.py==12.4.0
pathlib2==2.3.5
pbr==5.4.4
pexpect==4.7.0
pickleshare==0.7.5
Pillow==6.2.1
plac==1.1.3
plotly==4.3.0
preshed==3.0.2
prometheus-client==0.7.1
prompt-toolkit==2.0.10
protobuf==3.11.2
ptyprocess==0.6.0
pyarrow==0.12.1  (GPU machines)
pyasn1==0.4.8
pyasn1-modules==0.2.8
pycparser==2.19  (GPU machines)
pydot==1.4.1
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.5.2
pynvrtc==9.2
PyOpenGL==3.1.4
PyOpenGL-accelerate==3.1.4
pyparsing==2.4.5
Pyphen==0.9.5
pyrsistent==0.15.6
python-dateutil==2.8.1
python-slugify==4.0.0
pytz==2019.3
PyWavelets==1.1.1
PyYAML==5.2
pyzmq==18.1.1
qtconsole==4.6.0
raven==6.10.0
regex==2020.1.8
requests==2.22.0
requests-oauthlib==1.3.0
requests-toolbelt==0.9.1
retrowrapper==0.3.0
retrying==1.3.3
rsa==4.0
s3transfer==0.3.1
sacremoses==0.0.38
scikit-image==0.16.2
scikit-learn==0.22
scikit-umfpack==0.3.2
scipy==1.4.1
seaborn==0.9.0
Send2Trash==1.5.0
sentencepiece==0.1.85
six==1.13.0
sklearn==0.0
soupsieve==1.9.5
spacy==2.2.3
srsly==0.2.0
sympy==1.4
tabulate==0.8.6
tensorboard==2.1.0
tensorboardX==2.0
tensorflow==2.1.0
tensorflow-estimator==2.1.0
termcolor==1.1.0
terminado==0.8.3
testpath==0.4.4
text-unidecode==1.3
textacy==0.9.1
thinc==7.3.1
tokenizers==0.2.0
toolz==0.10.0
torch==1.4.0
torchtext==0.5.0
torchvision==0.5.0
tornado==6.0.3
tqdm==4.40.0
traitlets==4.3.3
transformers==2.3.0
urllib3==1.24.3
uWSGI==2.0.18
virtualenv==16.7.8
wasabi==0.4.2
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.16.0
widgetsnbextension==3.5.1
wrapt==1.11.2
xgboost==0.90
zipp==0.6.0
zmq==0.0.0
```


## PyTorch-1.3

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v10.0.130 | CuDNN 7.6.3
GPU2 | Cuda v10.0.130 | CuDNN 7.6.3

Python packages:

```bash
absl-py==0.8.1
annoy==1.16.2
args==0.1.0
astor==0.8.0
atari-py==0.2.6
attrs==19.3.0
backcall==0.1.0
beautifulsoup4==4.8.2
bleach==3.1.0
blis==0.4.1
boto3==1.11.7
botocore==1.14.7
Bottleneck==1.3.1
box2d-py==2.3.8
cachetools==3.1.1
catalogue==0.0.8
certifi==2019.11.28
cffi==1.13.2  (GPU machines)
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==1.2.2
cudf-cuda100==0.6.1  (GPU machines)
cuml-cuda100==0.6.1  (GPU machines)
cupy==7.0.0  (GPU machines)
cupy-cuda100==7.0.0  (GPU machines)
cycler==0.10.0
cymem==2.0.3
Cython==0.29.14
cytoolz==0.10.1
dataclasses==0.7
decorator==4.4.1
defusedxml==0.6.0
dlib==19.18.0
docutils==0.15.2
entrypoints==0.3
fastai==1.0.60
fastprogress==0.2.2
fastrlock==0.4  (GPU machines)
Flask==1.1.1
floyd-cli==0.11.17
funcsigs==1.0.2
future==0.18.2
gast==0.2.2
google-auth==1.7.2
google-auth-oauthlib==0.4.1
google-pasta==0.1.8
grpcio==1.25.0
gym==0.15.4
gym-retro==0.7.0
h5py==2.10.0
idna==2.8
imageio==2.6.1
importlib-metadata==1.2.0
incremental==17.5.0
ipykernel==5.1.3
ipython==7.10.1
ipython-genutils==0.2.0
ipywidgets==7.5.1
itsdangerous==1.1.0
jedi==0.15.1
jellyfish==0.7.2
Jinja2==2.10.3
jmespath==0.9.4
joblib==0.14.0
json5==0.8.5
jsonschema==3.2.0
jupyter==1.0.0
jupyter-client==5.3.4
jupyter-console==6.0.0
jupyter-core==4.6.1
jupyterlab==1.2.3
jupyterlab-server==1.0.6
kaggle==1.5.6
Keras==2.3.1
Keras-Applications==1.0.8
Keras-Preprocessing==1.1.0
kiwisolver==1.1.0
llvmlite==0.30.0  (GPU machines)
Markdown==3.1.1
MarkupSafe==1.1.1
marshmallow==2.20.5
matplotlib==3.1.2
menpo==0.9.2
mistune==0.8.4
mock==3.0.5
more-itertools==8.0.0
mpmath==1.1.0
murmurhash==1.0.2
nbconvert==5.6.1
nbformat==4.4.0
networkx==2.4
nltk==3.4.5
notebook==6.0.3
numba==0.41.0  (GPU machines)
numexpr==2.7.1
numpy==1.17.4
nvidia-ml-py3==7.352.0
nvstrings-cuda100==0.3.0.post1  (GPU machines)
oauthlib==3.1.0
opencv-contrib-python==3.4.0.12
opencv-python==4.1.2.30
opt-einsum==3.1.0
packaging==20.0
pandas==0.25.3
pandocfilters==1.4.2
parso==0.5.1
path==13.1.0
path.py==12.4.0
pathlib2==2.3.5
pbr==5.4.4
pexpect==4.7.0
pickleshare==0.7.5
Pillow==6.2.1
plac==1.1.3
plotly==4.3.0
preshed==3.0.2
prometheus-client==0.7.1
prompt-toolkit==2.0.10
protobuf==3.11.1
ptyprocess==0.6.0
pyarrow==0.12.1  (GPU machines)
pyasn1==0.4.8
pyasn1-modules==0.2.7
pycparser==2.19  (GPU machines)
pydot==1.4.1
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.5.2
pynvrtc==9.2
PyOpenGL==3.1.4
PyOpenGL-accelerate==3.1.4
pyparsing==2.4.5
Pyphen==0.9.5
pyrsistent==0.15.6
python-dateutil==2.8.1
python-slugify==4.0.0
pytz==2019.3
PyWavelets==1.1.1
PyYAML==5.2
pyzmq==18.1.1
qtconsole==4.6.0
raven==6.10.0
regex==2020.1.8
requests==2.22.0
requests-oauthlib==1.3.0
requests-toolbelt==0.9.1
retrowrapper==0.3.0
retrying==1.3.3
rsa==4.0
s3transfer==0.3.1
sacremoses==0.0.38
scikit-image==0.16.2
scikit-learn==0.22
scikit-umfpack==0.3.2
scipy==1.3.3
seaborn==0.9.0
Send2Trash==1.5.0
sentencepiece==0.1.85
six==1.13.0
sklearn==0.0
soupsieve==1.9.5
spacy==2.2.3
srsly==0.2.0
sympy==1.4
tabulate==0.8.6
tensorboard==2.0.2
tensorboardX==2.0
tensorflow==2.0.0
tensorflow-estimator==2.0.1
termcolor==1.1.0
terminado==0.8.3
testpath==0.4.4
text-unidecode==1.3
textacy==0.9.1
thinc==7.3.1
tokenizers==0.2.0
toolz==0.10.0
torch==1.3.1
torchtext==0.4.0
torchvision==0.4.2
tornado==6.0.3
tqdm==4.40.0
traitlets==4.3.3
transformers==2.3.0
urllib3==1.24.3
uWSGI==2.0.18
virtualenv==16.7.8
wasabi==0.4.2
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.16.0
widgetsnbextension==3.5.1
wrapt==1.11.2
xgboost==0.90
zipp==0.6.0
zmq==0.0.0
```


## PyTorch-1.2

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v10.0.130 | CuDNN 7.6.3
GPU2 | Cuda v10.0.130 | CuDNN 7.6.3

Python packages:

```bash
absl-py==0.8.1
annoy==1.16.2
args==0.1.0
astor==0.8.0
atari-py==0.2.6
attrs==19.3.0
backcall==0.1.0
beautifulsoup4==4.8.2
bleach==3.1.0
blis==0.4.1
boto3==1.11.7
botocore==1.14.7
Bottleneck==1.3.1
box2d-py==2.3.8
cachetools==3.1.1
catalogue==0.0.8
certifi==2019.11.28
cffi==1.13.2  (GPU machines)
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==1.2.2
cudf-cuda100==0.6.1  (GPU machines)
cuml-cuda100==0.6.1  (GPU machines)
cupy==7.0.0  (GPU machines)
cupy-cuda100==7.0.0  (GPU machines)
cycler==0.10.0
cymem==2.0.3
Cython==0.29.14
cytoolz==0.10.1
dataclasses==0.7
decorator==4.4.1
defusedxml==0.6.0
dlib==19.18.0
docutils==0.15.2
entrypoints==0.3
fastai==1.0.60
fastprogress==0.2.2
fastrlock==0.4  (GPU machines)
Flask==1.1.1
floyd-cli==0.11.17
funcsigs==1.0.2
future==0.18.2
gast==0.2.2
google-auth==1.7.2
google-auth-oauthlib==0.4.1
google-pasta==0.1.8
grpcio==1.25.0
gym==0.15.4
gym-retro==0.7.0
h5py==2.10.0
idna==2.8
imageio==2.6.1
importlib-metadata==1.2.0
incremental==17.5.0
ipykernel==5.1.3
ipython==7.10.1
ipython-genutils==0.2.0
ipywidgets==7.5.1
itsdangerous==1.1.0
jedi==0.15.1
jellyfish==0.7.2
Jinja2==2.10.3
jmespath==0.9.4
joblib==0.14.0
json5==0.8.5
jsonschema==3.2.0
jupyter==1.0.0
jupyter-client==5.3.4
jupyter-console==6.0.0
jupyter-core==4.6.1
jupyterlab==1.2.3
jupyterlab-server==1.0.6
kaggle==1.5.6
Keras==2.3.1
Keras-Applications==1.0.8
Keras-Preprocessing==1.1.0
kiwisolver==1.1.0
llvmlite==0.30.0  (GPU machines)
Markdown==3.1.1
MarkupSafe==1.1.1
marshmallow==2.20.5
matplotlib==3.1.2
menpo==0.9.2
mistune==0.8.4
mock==3.0.5
more-itertools==8.0.0
mpmath==1.1.0
murmurhash==1.0.2
nbconvert==5.6.1
nbformat==4.4.0
networkx==2.4
nltk==3.4.5
notebook==6.0.3
numba==0.41.0  (GPU machines)
numexpr==2.7.1
numpy==1.17.4
nvidia-ml-py3==7.352.0
nvstrings-cuda100==0.3.0.post1  (GPU machines)
oauthlib==3.1.0
opencv-contrib-python==3.4.0.12
opencv-python==4.1.2.30
opt-einsum==3.1.0
packaging==20.0
pandas==0.25.3
pandocfilters==1.4.2
parso==0.5.1
path==13.1.0
path.py==12.4.0
pathlib2==2.3.5
pbr==5.4.4
pexpect==4.7.0
pickleshare==0.7.5
Pillow==6.2.1
plac==1.1.3
plotly==4.3.0
preshed==3.0.2
prometheus-client==0.7.1
prompt-toolkit==2.0.10
protobuf==3.11.1
ptyprocess==0.6.0
pyarrow==0.12.1  (GPU machines)
pyasn1==0.4.8
pyasn1-modules==0.2.7
pycparser==2.19  (GPU machines)
pydot==1.4.1
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.5.2
pynvrtc==9.2
PyOpenGL==3.1.4
PyOpenGL-accelerate==3.1.4
pyparsing==2.4.5
Pyphen==0.9.5
pyrsistent==0.15.6
python-dateutil==2.8.1
python-slugify==4.0.0
pytz==2019.3
PyWavelets==1.1.1
PyYAML==5.2
pyzmq==18.1.1
qtconsole==4.6.0
raven==6.10.0
regex==2020.1.8
requests==2.22.0
requests-oauthlib==1.3.0
requests-toolbelt==0.9.1
retrowrapper==0.3.0
retrying==1.3.3
rsa==4.0
s3transfer==0.3.1
sacremoses==0.0.38
scikit-image==0.16.2
scikit-learn==0.22
scikit-umfpack==0.3.2
scipy==1.3.3
seaborn==0.9.0
Send2Trash==1.5.0
sentencepiece==0.1.85
six==1.13.0
sklearn==0.0
soupsieve==1.9.5
spacy==2.2.3
srsly==0.2.0
sympy==1.4
tabulate==0.8.6
tensorboard==2.0.2
tensorboardX==1.9
tensorflow==2.0.0
tensorflow-estimator==2.0.1
termcolor==1.1.0
terminado==0.8.3
testpath==0.4.4
text-unidecode==1.3
textacy==0.9.1
thinc==7.3.1
tokenizers==0.2.0
toolz==0.10.0
torch==1.2.0
torchtext==0.4.0
torchvision==0.4.0
tornado==6.0.3
tqdm==4.40.0
traitlets==4.3.3
transformers==2.3.0
urllib3==1.24.3
uWSGI==2.0.18
virtualenv==16.7.8
wasabi==0.4.2
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.16.0
widgetsnbextension==3.5.1
wrapt==1.11.2
xgboost==0.90
zipp==0.6.0
zmq==0.0.0
```


## PyTorch-1.1

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v9.1.85 | CuDNN 7.1.2
GPU2 | Cuda v9.1.85 | CuDNN 7.1.2

Python packages:

```bash
absl-py==0.8.0
annoy==1.16.0
args==0.1.0
astor==0.8.0
atari-py==0.2.6
attrs==19.1.0
backcall==0.1.0
beautifulsoup4==4.8.0
bleach==3.0.2
blis==0.2.4
Bottleneck==1.2.1
box2d-py==2.3.8
cachetools==3.1.1
certifi==2019.6.16
cffi==1.12.3  (GPU machines)
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==1.2.1  (GPU machines)
cudf-cuda92==0.6.1  (GPU machines)
cuml-cuda92==0.6.1  (GPU machines)
cupy==5.1.0         (GPU machines)
cupy-cuda92==6.3.0  (GPU machines)
cycler==0.10.0
cymem==2.0.2
Cython==0.29.2
cytoolz==0.10.0
dataclasses==0.6
decorator==4.3.0
defusedxml==0.5.0   (GPU machines)
dlib==19.17.0
entrypoints==0.2.3
fastai==1.0.57
fastprogress==0.1.21
fastrlock==0.4  (GPU machines)
Flask==1.1.0
floyd-cli==0.11.17
funcsigs==1.0.2
future==0.17.1
gast==0.2.2
google-pasta==0.1.7
grpcio==1.23.0
gym==0.14.0
gym-retro==0.7.0
h5py==2.9.0
idna==2.8
imageio==2.5.0
importlib-metadata==0.8
incremental==17.5.0
ipykernel==5.1.0
ipython==7.2.0
ipython-genutils==0.2.0
ipywidgets==7.4.2
itsdangerous==1.1.0
jedi==0.13.2
jellyfish==0.6.1
Jinja2==2.10.1
joblib==0.13.2
json5==0.8.5
jsonschema==3.0.2
jupyter==1.0.0
jupyter-client==5.2.4
jupyter-console==6.0.0
jupyter-core==4.4.0
jupyterlab==1.0.9
jupyterlab-server==1.0.6
kaggle==1.5.5
Keras==2.2.4
Keras-Applications==1.0.8
Keras-Preprocessing==1.1.0
kiwisolver==1.0.1
llvmlite==0.29.0  (GPU machines)
Markdown==3.1.1
MarkupSafe==1.1.0
marshmallow==2.20.2
matplotlib==3.0.2
menpo==0.9.2
mistune==0.8.4
mock==3.0.5
mpmath==1.1.0
murmurhash==1.0.2
nbconvert==5.4.0
nbformat==4.4.0
networkx==2.3
nltk==3.4.5
notebook==5.6.0
numba==0.41.0  (GPU machines)
numexpr==2.7.0
numpy==1.15.4
nvidia-ml-py3==7.352.0  (GPU machines)
nvstrings-cuda92==0.3.0.post1  (GPU machines)
opencv-contrib-python==3.4.0.12
opencv-python==4.1.0.25
packaging==19.1
pandas==0.23.4
pandocfilters==1.4.2
parso==0.3.1
path.py==11.5.0
pathlib2==2.3.4
pbr==5.4.2
pexpect==4.6.0
pickleshare==0.7.5
Pillow==5.4.0
plac==0.9.6
plotly==4.1.0
preshed==2.0.1
prometheus-client==0.5.0
prompt-toolkit==2.0.7
protobuf==3.9.1
ptyprocess==0.6.0
pyarrow==0.12.1  (GPU machines)
pycparser==2.19  (GPU machines)
pydot==1.4.1
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.3.1
pynvrtc==9.2
PyOpenGL==3.1.0
PyOpenGL-accelerate==3.1.0
pyparsing==2.3.0
Pyphen==0.9.5
pyrsistent==0.15.4
python-dateutil==2.7.5
python-slugify==3.0.3
pytz==2018.7
PyWavelets==1.0.3
PyYAML==3.13
pyzmq==17.1.2
qtconsole==4.4.3
raven==6.10.0
requests==2.22.0
requests-toolbelt==0.9.1
retrowrapper==0.3.0
retrying==1.3.3
scikit-image==0.15.0
scikit-learn==0.20.2
scikit-umfpack==0.3.2
scipy==1.2.0
seaborn==0.9.0
Send2Trash==1.5.0
six==1.12.0
sklearn==0.0
spacy==2.1.8
srsly==0.1.0
soupsieve==1.9.3
sympy==1.3
tabulate==0.8.3
tensorboard==1.14.0
tensorboardX==1.8
tensorflow==1.14.0
tensorflow-estimator==1.14.0
termcolor==1.1.0
terminado==0.8.1
testpath==0.4.2
text-unidecode==1.2
textacy==0.8.0
tflearn==0.3.2
thinc==7.0.8
toolz==0.10.0
torch==1.1.0
torchtext==0.4.0
torchvision==0.3.0
tornado==5.1.1
tqdm==4.35.0
traitlets==4.3.2
typing==3.7.4.1
urllib3==1.24.3
uWSGI==2.0.18
virtualenv==16.2.0
wasabi==0.2.2
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.15.5
widgetsnbextension==3.4.2
wrapt==1.11.2
xgboost==0.81
zipp==0.3.3  (GPU machines)
zmq==0.0.0
```


## PyTorch-1.0

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v9.1.85 | CuDNN 7.1.2
GPU2 | Cuda v9.1.85 | CuDNN 7.1.2

!!! important "PyTorch + MAGMA"
	PyTorch is compiled from source to provide [MAGMA](https://developer.nvidia.com/magma) support.

Python packages:

```bash
absl-py==0.7.1
annoy==1.15.2
args==0.1.0
astor==0.7.1
atari-py==0.1.7
backcall==0.1.0
beautifulsoup4==4.7.1
bleach==3.0.2
blis==0.2.4
Bottleneck==1.2.1
box2d-py==2.3.8
cachetools==3.1.0
certifi==2019.3.9
cffi==1.12.3
chardet==3.0.4
click==6.7
clint==0.5.1
cudf-cuda92==0.6.1  (GPU machines)
cuml-cuda92==0.6.1  (GPU machines)
cupy==5.1.0  (GPU machines)
cupy-cuda92==5.4.0  (GPU machines)
cycler==0.10.0
cymem==2.0.2
Cython==0.29.2
cytoolz==0.9.0.1
dataclasses==0.6
decorator==4.3.0
defusedxml==0.5.0
dlib==19.17.0
entrypoints==0.2.3
fastai==1.0.51
fastprogress==0.1.21
fastrlock==0.4  (GPU machines)
Flask==1.0.2
floyd-cli==0.11.17
ftfy==4.4.3
funcsigs==1.0.2
future==0.17.1
gast==0.2.2
grpcio==1.20.1
gym==0.12.1
gym-retro==0.7.0
h5py==2.9.0
html5lib==1.0.1
idna==2.8
ijson==2.3
imageio==2.5.0
importlib-metadata==0.8
incremental==17.5.0
ipykernel==5.1.0
ipython==7.2.0
ipython-genutils==0.2.0
ipywidgets==7.4.2
itsdangerous==1.1.0
jedi==0.13.2
Jinja2==2.10
jsonschema==2.6.0
jupyter==1.0.0
jupyter-client==5.2.4
jupyter-console==6.0.0
jupyter-core==4.4.0
jupyterlab==0.35.4
jupyterlab-server==0.2.0
kaggle==1.5.3
Keras==2.2.4
Keras-Applications==1.0.7
Keras-Preprocessing==1.0.9
kiwisolver==1.0.1
llvmlite==0.28.0
Markdown==3.1
MarkupSafe==1.1.0
marshmallow==2.19.2
matplotlib==3.0.2
menpo==0.8.1
mistune==0.8.4
mock==2.0.0
mpmath==1.1.0
murmurhash==1.0.2
mwparserfromhell==0.5.3
nbconvert==5.4.0
nbformat==4.4.0
networkx==2.3
nltk==3.4.1
notebook==5.6.0
numba==0.41.0
numexpr==2.6.9
numpy==1.15.4
nvidia-ml-py3==7.352.0  (GPU machines)
nvstrings-cuda92==0.3.0.post1  (GPU machines)
opencv-contrib-python==3.4.0.12
packaging==19.0
pandas==0.23.4
pandocfilters==1.4.2
parso==0.3.1
path.py==11.5.0
pathlib2==2.3.3
pbr==5.1.3
pexpect==4.6.0
pickleshare==0.7.5
Pillow==5.4.0
plac==0.9.6
plotly==3.8.1
preshed==2.0.1
prometheus-client==0.5.0
prompt-toolkit==2.0.7
protobuf==3.7.1
ptyprocess==0.6.0
pyarrow==0.12.1
pycparser==2.19
pydot==1.4.1
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.3.1
pynvrtc==9.2
PyOpenGL==3.1.0
PyOpenGL-accelerate==3.1.0
pyparsing==2.3.0
Pyphen==0.9.5
python-dateutil==2.7.5
python-Levenshtein==0.12.0
python-slugify==3.0.2
pytz==2018.7
PyWavelets==1.0.3
PyYAML==3.13
pyzmq==17.1.2
qtconsole==4.4.3
raven==6.10.0
requests==2.21.0
requests-toolbelt==0.9.1
retrowrapper==0.3.0
retrying==1.3.3
scikit-image==0.15.0
scikit-learn==0.20.2
scikit-umfpack==0.3.2
scipy==1.2.0
seaborn==0.9.0
Send2Trash==1.5.0
six==1.12.0
sklearn==0.0
soupsieve==1.9.1
spacy==2.1.3
srsly==0.0.5
sympy==1.3
tabulate==0.8.3
tensorboard==1.13.1
tensorboardX==1.2
tensorflow==1.13.1
tensorflow-estimator==1.13.0
termcolor==1.1.0
terminado==0.8.1
testpath==0.4.2
text-unidecode==1.2
textacy==0.6.3
tflearn==0.3.2
thinc==7.0.4
toolz==0.9.0
torch==1.0.1.post2
torchtext==0.3.1
torchvision==0.2.1
tornado==5.1.1
tqdm==4.31.1
traitlets==4.3.2
typing==3.6.6
urllib3==1.24.2
uWSGI==2.0.17
virtualenv==16.2.0
wasabi==0.2.1
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.15.2
widgetsnbextension==3.4.2
xgboost==0.81
zipp==0.3.3  (GPU machines)
zmq==0.0.0
```

## PyTorch-0.4

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v9.1.85 | CuDNN 7.1.2
GPU2 | Cuda v9.1.85 | CuDNN 7.1.2

Python packages:
```bash
absl-py==0.4.1
annoy==1.12.0
args==0.1.0
astor==0.7.1
atari-py==0.1.1
backcall==0.1.0
bleach==2.1.4
Box2D-kengz==2.3.3
cachetools==2.1.0
certifi==2018.8.13
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==0.5.3
cupy==4.3.0  (GPU machines)
cupy-cuda91==4.3.0  (GPU machines)
cycler==0.10.0
cymem==1.31.2
Cython==0.28.5
cytoolz==0.9.0.1
dask==0.18.2
decorator==4.3.0
dill==0.2.8.2
dlib==19.15.0
entrypoints==0.2.3
fastrlock==0.3  (GPU machines)
Flask==1.0.2
floyd-cli==0.11.11
ftfy==4.4.3
future==0.16.0
gast==0.2.0
grpcio==1.14.2
gym==0.10.5
gym-retro==0.5.6
h5py==2.8.0
html5lib==1.0.1
idna==2.7
ijson==2.3
incremental==17.5.0
intel-openmp==2018.0.3  (GPU machines)
ipykernel==4.8.2
ipython==6.5.0
ipython-genutils==0.2.0
ipywidgets==7.4.0
itsdangerous==0.24
jedi==0.12.1
Jinja2==2.10
jsonschema==2.6.0
jupyter==1.0.0
jupyter-client==5.2.3
jupyter-console==5.2.0
jupyter-core==4.4.0
jupyterlab==0.33.8
jupyterlab-launcher==0.11.2
kaggle==1.4.6
Keras==2.2.0
Keras-Applications==1.0.2
Keras-Preprocessing==1.0.1
kiwisolver==1.0.1
Markdown==2.6.11
MarkupSafe==1.0
marshmallow==2.15.4
matplotlib==2.2.3
menpo==0.8.1
mistune==0.8.3
mkl==2018.0.3  (GPU machines)
mkl-devel==2018.0.3  (GPU machines)
mkl-include==2018.0.3  (GPU machines)
mpmath==1.0.0
msgpack==0.5.6
msgpack-numpy==0.4.3.1
murmurhash==0.28.0
nbconvert==5.3.1
nbformat==4.4.0
networkx==2.1
nltk==3.3
notebook==5.6.0
numpy==1.15.1
opencv-contrib-python==3.4.0.12
pandas==0.23.4
pandocfilters==1.4.2
parso==0.3.1
path.py==11.0.1
pathlib2==2.3.2
pexpect==4.6.0
pickleshare==0.7.4
Pillow==5.2.0
plac==0.9.6
plotly==3.1.1
preshed==1.0.1
prometheus-client==0.3.1
prompt-toolkit==1.0.15
protobuf==3.6.1
ptyprocess==0.6.0
pydot==1.2.4
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.2.0
pynvrtc==9.2
PyOpenGL==3.1.0
PyOpenGL-accelerate==3.1.0
pyparsing==2.2.0
Pyphen==0.9.4
python-dateutil==2.7.3
python-Levenshtein==0.12.0
pytz==2018.5
PyWavelets==0.5.2
PyYAML==3.13
pyzmq==17.1.2
qtconsole==4.4.1
raven==6.9.0
regex==2017.4.5
requests==2.19.1
requests-toolbelt==0.8.0
retrowrapper==0.2.1
retrying==1.3.3
scikit-image==0.14.0
scikit-learn==0.19.2
scikit-umfpack==0.3.1
scipy==1.1.0
seaborn==0.9.0
Send2Trash==1.5.0
simplegeneric==0.8.1
six==1.11.0
sklearn==0.0
spacy==2.0.12
sympy==1.2
tabulate==0.8.2
tensorboard==1.9.0
tensorboardX==1.2
tensorflow==1.9.0
termcolor==1.1.0
terminado==0.8.1
testpath==0.3.1
textacy==0.6.2
tflearn==0.3.2
thinc==6.10.3
toolz==0.9.0
torch==0.4.1 (v0.5.0a0+a24163a GPU machines)
torchtext==0.2.3
torchvision==0.2.1
tornado==5.1
tqdm==4.25.0
traitlets==4.3.2
typing==3.6.6  (CPU machines)
ujson==1.35
Unidecode==1.0.22
urllib3==1.22
uWSGI==2.0.17
virtualenv==16.0.0
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.14.1
widgetsnbextension==3.4.0
wrapt==1.10.11
xgboost==0.80
zmq==0.0.0
```

## PyTorch-0.3

Nvidia Setup:

Machine | Nvidia CUDA | Nvidia CuDNN
--------|-------------|-------------
GPU | Cuda v9.1.85 | CuDNN 7.1.2
GPU2 | Cuda v9.1.85 | CuDNN 7.1.2

Python packages:
```bash
absl-py==0.4.1
annoy==1.12.0
args==0.1.0
astor==0.7.1
atari-py==0.1.1
backcall==0.1.0
bleach==2.1.4
Box2D-kengz==2.3.3
cachetools==2.1.0
certifi==2018.8.13
chardet==3.0.4
click==6.7
clint==0.5.1
cloudpickle==0.5.3
cupy==4.3.0  (GPU machines)
cupy-cuda91==4.3.0  (GPU machines)
cycler==0.10.0
cymem==1.31.2
Cython==0.28.5
cytoolz==0.9.0.1
dask==0.18.2
decorator==4.3.0
dill==0.2.8.2
dlib==19.15.0
entrypoints==0.2.3
fastrlock==0.3  (GPU machines)
Flask==1.0.2
floyd-cli==0.11.11
ftfy==4.4.3
future==0.16.0
gast==0.2.0
grpcio==1.14.2
gym==0.10.5
gym-retro==0.5.6
h5py==2.8.0
html5lib==1.0.1
idna==2.7
ijson==2.3
incremental==17.5.0
ipykernel==4.8.2
ipython==6.5.0
ipython-genutils==0.2.0
ipywidgets==7.4.0
itsdangerous==0.24
jedi==0.12.1
Jinja2==2.10
jsonschema==2.6.0
jupyter==1.0.0
jupyter-client==5.2.3
jupyter-console==5.2.0
jupyter-core==4.4.0
jupyterlab==0.33.8
jupyterlab-launcher==0.11.2
kaggle==1.4.6
Keras==2.2.0
Keras-Applications==1.0.2
Keras-Preprocessing==1.0.1
kiwisolver==1.0.1
Markdown==2.6.11
MarkupSafe==1.0
marshmallow==2.15.4
matplotlib==2.2.3
menpo==0.8.1
mistune==0.8.3
mpmath==1.0.0
msgpack==0.5.6
msgpack-numpy==0.4.3.1
murmurhash==0.28.0
nbconvert==5.3.1
nbformat==4.4.0
networkx==2.1
nltk==3.3
notebook==5.6.0
numpy==1.15.1
opencv-contrib-python==3.4.0.12
pandas==0.23.4
pandocfilters==1.4.2
parso==0.3.1
path.py==11.0.1
pathlib2==2.3.2
pexpect==4.6.0
pickleshare==0.7.4
Pillow==5.2.0
plac==0.9.6
plotly==3.1.1
preshed==1.0.1
prometheus-client==0.3.1
prompt-toolkit==1.0.15
protobuf==3.6.1
ptyprocess==0.6.0
pydot==1.2.4
pyemd==0.5.1
pyglet==1.3.2
Pygments==2.2.0
pynvrtc==9.2
PyOpenGL==3.1.0
PyOpenGL-accelerate==3.1.0
pyparsing==2.2.0
Pyphen==0.9.4
python-dateutil==2.7.3
python-Levenshtein==0.12.0
pytz==2018.5
PyWavelets==0.5.2
PyYAML==3.13
pyzmq==17.1.2
qtconsole==4.4.1
raven==6.9.0
regex==2017.4.5
requests==2.19.1
requests-toolbelt==0.8.0
retrowrapper==0.2.1
retrying==1.3.3
scikit-image==0.14.0
scikit-learn==0.19.2
scikit-umfpack==0.3.1
scipy==1.1.0
seaborn==0.9.0
Send2Trash==1.5.0
simplegeneric==0.8.1
six==1.11.0
sklearn==0.0
spacy==2.0.12
sympy==1.2
tabulate==0.8.2
tensorboard==1.9.0
tensorboardX==1.2
tensorflow==1.9.0
termcolor==1.1.0
terminado==0.8.1
testpath==0.3.1
textacy==0.6.2
tflearn==0.3.2
thinc==6.10.3
toolz==0.9.0
torch==0.3.1
torchtext==0.2.3
torchvision==0.2.1
tornado==5.1
tqdm==4.25.0
traitlets==4.3.2
ujson==1.35
Unidecode==1.0.22
urllib3==1.22
uWSGI==2.0.17
virtualenv==16.0.0
wcwidth==0.1.7
webencodings==0.5.1
Werkzeug==0.14.1
widgetsnbextension==3.4.0
wrapt==1.10.11
xgboost==0.80
zmq==0.0.0
```