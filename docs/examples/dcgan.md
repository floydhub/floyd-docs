Deep Convolution Generative Adversarial Network is one of the first approach which made GAN "stable" and usable to learn features from images with unsupervised learning. This project is a porting from the [pytorch/examples/dcgan](https://github.com/pytorch/examples/tree/master/dcgan). At the end of this example you will be able to use DCGAN for generating images from your dataset.

In this guide we will train a pytorch model in an unsupervised task and use it to
generate images from an input latent vector Z. Finally we will deploy the trained model as a
REST endpoint that can be used to generate images in real time.

## Project setup
/* TODO: change github page*/
The code for this project is available on Floyd's [Github page](https://github.com/floydhub/dcgan). Once [logged in](../commands/login), clone the project and [initialize](../commands/init) a floyd project.

```bash
$ git clone https://github.com/floydhub/dcgan
$ cd dcgan
$ floyd init dcgan
```

## Training

### Dataset
/* TODO: change dataset floydhub page*/
For this project we will use the [Labeled Faces in the Wild Home](http://vis-www.cs.umass.edu/lfw/) aka LFW for the training.
Since we are learning in an unsupervised regime, there is not a train/dev/test split, but we use the BCE Loss Error of the Discriminator and Generator as good metrics to learn(minmax game strategy from Game Theory), moreover we can visualize the generated images every epoch.
This preprocessed dataset is available publicly on
[FloydHub](https://www.floydhub.com/floydhub/datasets/lfw/1).


### Training
/* TODO: change dataset floydhub page*/
You can train the DCGAN model by running `main.py` script with required
parameters. Below is the [command](../commands/run) to start a training job on Floyd:

```bash
$ floyd run --gpu --env pytorch --data floydhub/datasets/lfw/1:lfw "python main.py --dataset lfw --dataroot /lfw --outf /output --cuda --ngpu 1 --niter 20"
```

Notes:
/* TODO: change dataset floydhub page*/
- The input dataset is passed using the `--data` parameter. This mounts the pre-processed
LFW dataset at `/lfw` path. You will notice that the dataroot parameter uses files
mounted in this path.
- The data name [floydhub/datasets/lfw/1](https://www.floydhub.com/floydhub/datasets/lfw/1)
points to the pre-processed dataset on FloydHub.
- The job is running on a gpu instance with cuda enabled (Because of the `--gpu` and `--cuda` flags ).
- This project uses pytorch installed on Python 2. (See the `--env` flag)

This job takes about 20 minutes to run and generate a model. You can follow along the progress
by using the [logs](../commands/logs.md) command. If you run the model with default value it will take about 1/5 minutes per epoch.

```bash
$ floyd logs <JOB_NAME> -t
```

Floyd saves any content stored in the `/output` directory after the job is
finished. This output can be used as a datasource in the next project.  To get
the name of the output generated by your job use the
[info](../commands/info.md) command.

```bash
$ floyd info <JOB_NAME>
```


## Evaluating

To evaluate your model you can run the `generate.py` script. The script needs the path of a checkpoint Generator model .
The output will be created in the folder you will provide as parameter(--outf) or in the `/output` default path to be Floydhub compliant.
Moreover you can provide a serialized Zvector(--Zvector) to experiment with latent Z vector arithmetic landscape and for analyzing the semantic information encoded during training.

```bash
floyd run --gpu --env pytorch -data <REPLACE_WITH_JOB_OUTPUT_NAME> "python generator.py --netG <REPLACE_WITH_MODEL_CHECKPOINT_PATH>"

# Provide a serialized Zvector
floyd run --gpu --env pytorch -data <REPLACE_WITH_JOB_OUTPUT_NAME> "python generator.py --netG <REPLACE_WITH_MODEL_CHECKPOINT_PATH> --Zvector <REPLACE_WITH_SERIALIZED_Z_VECTOR_PATH>"
```

You can track the status of the run with the status or logs command.

```bash
$ floyd status <JOB_NAME>
$ floyd logs <JOB_NAME> -t
```


## Improving your model

You may notice that the output does not look great. In fact, the algorithm have not yet learned how to correctly represent a face.
That is because we ran the training for a small number of iterations. To train a fully working model, try the training step again, this time by setting the flag `--niter` to a large value, such as 100. In general, about 100 epoch(or even more, much more!) are necessary to have an accetable model. (Note: This takes a few hours to run on the GPU instance!).
Keep in mind that *all the class of generative networks are not neither stable nor production ready*, this is a exciting field of research and everyone can contribute with new ideas.

## Evaluate pre-trained models
/* Change output*/
If you want to try out a pre-trained model, FloydHub has a public job output for
this. You can mount it with job output name:
[floydhub/dcgan/1/output](https://www.floydhub.com/floydhub/projects/dcgan/1/output)
.

```bash
floyd run --gpu --env pytorch -data floydhub/dcgan/1/output:/model "python generator.py --netG /model/netG_epoch_99.pth"
```

This model should perform better on the given inputs compared to the previous one.


## Serve model through REST API

FloydHub supports seving mode for demo and testing purpose. Before serving your model through REST API,
you need to create a `floyd_requirements.txt` and declare the flask requirement in it. If you run a job
with `--mode serve` flag, FloydHub will run the `app.py` file in your project
and attach it to a dynamic service endpoint:


/* Change output*/
```bash
floyd run --gpu --mode serve --env pytorch --data floydhub/dcgan/1/output:/model:model
```

The above command will print out a service endpoint for this job in your terminal console.

The service endpoint will take couple minutes to become ready. Once it's up, you can interact with the model by sending serialized Zvector file with a POST request or simply generate images from random noise:

```bash
# e.g. of a GET req
curl -X GET -o <NAME_&_PATH_DOWNLOADED_IMG> -F "ckp=<MODEL_CHECKPOINT>" <SERVICE_ENDPOINT>
curl -X GET -o prova.png -F "ckp=netG_epoch_69.pth" https://www.floydhub.com/expose/hellllllllllllllo!!!!

# e.g. of a POST req
curl -X POST -o <NAME_&_PATH_DOWNLOADED_IMG> -F "file=@<ZVECTOR_SERIALIZED_PATH>" <SERVICE_ENDPOINT>
curl -X POST -o prova.png -F "file=@./parameter/zvector.pth" https://www.floydhub.com/expose/hellllllllllllllo!!!!
```

Any job running in serving mode will stay up until it reaches maximum runtime. So
once you are done testing, remember to shutdown the job.

*Note that this feature is in preview mode and is not production ready yet*


## What Next?

In the original paper the model was trained on the [LSUN](http://www.yf.io/p/lsun) dataset and the learned features were used to perform an image classification task on ImageNet-1k dataset. DCGAN was one of the first "stable" model based on GAN and the first which tried to learn features from images in an unsupervised regime.

{!contributing.md!}