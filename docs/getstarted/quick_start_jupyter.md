## Quick preparation checklist

- You must have a [FloydHub account](https://www.floydhub.com/login)
- You must have `floyd-cli` [installed on your computer](../guides/basics/install.md)
- You must [log in to FloydHub through the CLI](../guides/basics/login.md)


## Quick Start

1. Visit https://www.floydhub.com/projects/create and create a FloydHub
   project:
   ![create jupyter notebook](../img/create_jupyter_project.jpg)

2. In your terminal, use Floyd CLI to initialize the project (be sure to use
   the name you gave the project in step one):

    ```
    $ floyd init my_jupyter_project

    Project "my_jupyter_project" initialized in current directory
    ```

3. Then, kick off your first Jupyter Notebook with `floyd run --gpu --mode
   jupyter`

    ```
    $ floyd run --mode jupyter

    Creating project run. Total upload size: 198.0B
    Syncing code ...
    [================================] 946/946 - 00:00:00

    JOB NAME
    -----------------------------------
    mckay/projects/my_jupyter_project/1

    Setting up your instance and waiting for Jupyter notebook to become available .............

    Path to jupyter notebook: https://floydlabs.com/notebooks/gaftzXTdaPtQtQ9NvEieNg
    ```

    This will open up a Jupyter Notebook in your browser. The notebook is
    running on FloyHub's GPU servers. Just like that, you're up and running!
