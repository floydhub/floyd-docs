Sometimes, your code might require your data to be available at a hardcoded location. Or you might want to combine multiple mounted datasources under a single directory. One way to do this would be to copy the data from the mounted locations to the destination, but this is inefficient for large data. [Symlinking](https://en.wikipedia.org/wiki/Symbolic_link) is a great solution for this.

### Example 1
Your data is mounted under `/vgg` using `--data floydhub/datasets/vgg-ilsvrc-19-layers/1:vgg`. However, your code expects the data to be present at `/home/data/vgg/2017`. Instead of copying the files, you can symlink the two locations

```bash
# NOTE: Ensure that /home/data/vgg/2017 already exists
$ ln -s /vgg/* /home/data/vgg/2017
```

Jupyter Notebook example:
![Symlink Jupyter](../../img/symlink_jupyter.jpg)

### Example 2

You have two datasources mounted under `/train` and `/test` respectively. Your Python script `train_and_eval.py` expects both the datasources to be available under the same parent directory, say `/data/train` and `/data/test`. You can symlink the datasources to the respective destinations.

To do this, we can follow one of two solutions.

**Solution 1**: Include the symlink commands as part of your `floyd run` command.

```bash
$ floyd run --data alice/datasets/imagenet-train/1:train --data alice/datasets/imagenet-test/1:test "mkdir /data && ln -s /train /data && ln -s /test /data && python train_and_eval.py"
```

This example chains a series of commands, which are executed in sequence: `mkdir`, `ln -s /train /data`, `ln -s /test /data` and `python train_and_eval.py`

**Solution 2**: Solution 1 can get unwieldy when there are many commands. An alternative would be to create a bash script (`run.sh`) with the sequence of commands and then execute this bash script.

`run.sh`
```bash
#!/bin/bash

# Create a /data directory
mkdir /data

# Symlink mounted data to their destinations
ln -s /train /data
ln -s /test /data

# Execute Python script
python train_and_eval.py
```

Execute the bash script using `floyd run`:

```bash
$ floyd run "bash run.sh"
```
