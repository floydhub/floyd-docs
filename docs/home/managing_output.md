## Storing output files

Most of the experiments generate output files. (eg. model files, evaluation output). In Floyd, any file 
or directory you create under `/output/` directory at run time will be available 
to you for download after the experiment finishes.

An example command for this:

```bash
$ floyd run "python 1_Introduction/helloworld.py > /output/tf-output.txt"
Syncing code ...
...
```

The file created under `/output` will be saved. You can refer this output with its 
ID. To get this id use the [info](../commands/info.md) command.

```bash
$ floyd info Faa2xpokjAfJL5Jd7vCVXo
-----------  ----------------------------------------------------
Run ID       Faa2xpokjAfJL5Jd7vCVXo
Output ID    VB9bF6vtyvrHLdUsFbUuvW
...
-----------  ----------------------------------------------------
```

## Using output as a data source

To use the output of a project as an input to another run you can pass the 
`Output ID` as the `--data` parameter in the [run](../commands/run.md) command.
The contents of this will be available at `/input` in the new job.

```bash
$ floyd run --data VB9bF6vtyvrHLdUsFbUuvW "python train_tf.py -lr 0.01 -output /output/model.bin"
Syncing code ...
...
```
