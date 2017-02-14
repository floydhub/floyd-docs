### Running on a GPU Instance

It is very easy to run your code on a GPU instance of Floyd. Just add `--gpu` flag 
to the floyd `run` command.

    $ floyd run --gpu "python 1_Introduction/helloworld.py > /output/tf-output.txt"
    Creating module. Uploading 20 files ...
    RUN ID                  NAME                 VERSION
    ----------------------  -----------------  ---------
    KYBMnXZo3DsGGCiRdcYNUc  narenst/tf-demo:4          4

Make sure your code is optimized to use the available GPU.
