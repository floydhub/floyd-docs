Initialize a Floyd project.

### Usage
```bash
floyd init PROJECT_NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| PROJECT_NAME    |         | Name of your project (No spaces. Use letters, numbers, dash and underscore)    |

### Description
Floyd tracks projects based on the location of your code. This command initializes a new project at the current directory and 
tracks all files and subdirectories. These files will be uploaded when you run your project on Floyd.

To initialize a new dataset you should use [floyd data init](data/#floyd-data-init) command.

The init command also creates a `.floydignore` file. Any files and directories you do not want Floyd to track can be added 
to this file. When you run your project on Floyd, these files will not be uploaded. More details on how floydignore 
file works is available [here](../home/floyd_ignore).

### Example
Initialize a floyd project in your project directory.
```bash
$ cd /code/project
$ floyd init style-transfer
Project "style-transfer" initialized in current directory
```

{!contributing.md!}
