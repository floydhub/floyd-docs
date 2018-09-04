# Floyd Config File

Floyd config file (floyd.yml) is a powerful tool you can use to automate and drive various workflows in FloydHub. It sits at the root directory of your project folder (directory where you ran floyd init). The config file should be written in standard YAML syntax.


## Provide default arguments for floyd run

Instead of having to type out all the command arguments everytime you want to create a FloydHub job from floyd CLI, you can save a set of default arguments in floyd.yml. With this, all you have to type next time is just `floyd run`.

For example, the following command:

```bash
floyd run --gpu --data mckay/datasets/mnist/1:mnist --env tensorflow-1.8 -m "CNN with 0.5 dropout" "python train_and_eval.py"
```

Can be simplified to just `floyd run` if you have the following floyd.yml created inside project root directory:

```yaml
machine: gpu
input:
  - source: mckay/datasets/mnist/1
    destination: mnist
env: tensorflow-1.8
description: CNN with 0.5 dropout
command: python train_and_eval.py
```

You can also override the arguments in `floyd run` comamnd to quickly test out a change. For example:

```bash
floyd run --cpu2 -m "CNN with 0.25 dropout"
```

is equivalent to the following with above mentioned floyd config file:

```bash
floyd run --cpu2 --data mckay/datasets/mnist/1:mnist --env tensorflow-1.8 -m "CNN with 0.25 dropout" "python train_and_eval.py"
```


## Predefined tasks for floyd run

Often times, you don't just run the same run command over and over for a
project. You might need to try out different command arguments for different
purposes. For example, trying out a complete different algorithm, creating jobs
to test a model, spinning up a serving job, etc.

To handle this use-case, the concept of task is added to floyd config file. It
also makes it really easy to share and document a set of predefined tasks for a
project with other collaborators.

Let's say we usually run the following commands within a project:

```bash
# create job to train a model
floyd run --gpu2 --env pytorch-0.4 -m "train with lstm" --data foo/datasets/wine-reviews/1:input "train.py /floyd/input/input"

# create job to test a model
floyd run --gpu --env pytorch-0.4 -m "evaluate model1" --data foo/projects/nlp/1:model --data foo/datasets/wine-reviews-test/1:test "python test.py --model /floyd/input/model --data /floyd/input/test"

# create job to serve a model
floyd run --cpu --mode serve --env pytorch-0.4 --data foo/projects/nlp/1:model
```

We can capture all these use-cases in floyd config file:

```yaml
env: pytorch-0.4

task:
  train:
    machine: gpu2
    description: train with lstm
    input:
      - source: foo/datasets/wine-reviews/1
        destination: input
    command: train.py /floyd/input/input

  test:
    machine: gpu
    description: evaluate model1
    input:
      - source: foo/projects/nlp
        destination: model
      - source: foo/datasets/wine-reviews-test/1
        destination: test
    command: test.py --model /floyd/input/model --data /floyd/input/test

  serve:
    machine: cpu
    mode: serve
    input:
      - source: foo/projects/nlp
        destination: model
```

To invoke a specific task, you can pass name of the task to `floyd run` command through '--task' argument:

```bash
floyd run --task train
floyd run --task test
floyd run --task serve
```

Noticed that in the floyd config file, environment pytorch-0.4 is defined outside of task block globally. This is how you share configs between all the tasks so you don't have to repeatedly define the same config in each task definition.


## Run on Floyd Button

Floyd config is also used to bootstrap projects for run on floyd button. You can read more about it in [Run on Floyd Button](./guides/run_on_floydhub_button.md) docs.


## Supported attributes

You can find a documented sample config with all supported attributes at [this link](https://github.com/floydhub/floyd-cli/blob/master/floyd/cli/default_floyd.yml).
