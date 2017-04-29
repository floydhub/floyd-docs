### Running on a GPU Instance

It is very simple to run your code on a GPU instance of Floyd. Just add `--gpu` flag 
to the floyd [run](../commands/run.md) command.


```bash
$ floyd run --gpu "python train_tf.py -lr 0.01 -output /output/model.bin"
Syncing code ...
RUN ID                  NAME                 VERSION
----------------------  -----------------  ---------
KYBMnXZo3DsGGCiRdcYNUc  floydhub/tf-demo:4         4
```

Just make sure your code is optimized to use the available GPU.

{!contributing.md!}
