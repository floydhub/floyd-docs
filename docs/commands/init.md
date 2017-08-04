Initialize a Floyd project.

### Usage
```bash
floyd init PROJECT_NAME
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| PROJECT_NAME    |         | Name of your project (Pick a name from the projects page in web dashboard) |

### Description

This command initializes the current directory for a given project name and tracks all the files and subdirectories. 
Make sure that the project name you enter here already exists in Floyd. In case the project name does not exist, 
the CLI will open the create project page in your browser.

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
