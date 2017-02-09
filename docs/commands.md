# Floyd Commands

| Command            | Description              |
| ------------------ | ------------------------ |
| [floyd init](/docs/commands#init)       | Create a local project   |
| floyd login        | Login to your Floyd account   |
| floyd logout        | Logout from your Floyd account   |
| floyd run          | Run a job on AWS     |
| floyd logs         | View the logs of a run job |
| floyd output       | View the output files of your job   |
| floyd status       | View the status of your jobs   |
| floyd stop       | Stop a running job   |


---------------------------------
## floyd init

### Description
Create a Floyd project in your local directory

### Usage
```bash
floyd init [OPTIONS]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--project`, `-p` |      | Name your project (No spaces. Use letters, numbers, dash and underscore)    |

### Extended Description
Create a Floyd project in your local directory. As you make changes to your code, 
Floyd will keep track of them and upload the latest version when you run your project.

### Examples
#### Create a project called my-project in your current dir
```bash
$ floyd init my-project
```

---------------------------------
## floyd login

### Description
Login to your Floyd account

### Usage
```bash
floyd login [OPTIONS]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--username`, `-u` |      | Username    |
| `--password`, `-p` |      | Password    |

### Extended Description

Login to your Floyd account. 

### Examples
#### Login using your username
```bash
$ floyd login --username johndoe
# You will be prompted for your password
```

---------------------------------
## floyd logout

### Description
Logout from your Floyd account

### Usage
```bash
floyd logout
```

### Extended Description

Logout from your Floyd account. 

### Examples
#### Logout
```bash
$ floyd logout
```

---------------------------------
## floyd run

### Description
Run the current version of your project on AWS

### Usage
```bash
floyd run [OPTIONS] [COMMAND]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--gpu` |      | If specified, runs the job on GPU on AWS    |
| command |      | Command to use to run your project    |

### Extended Description
Runs the current version of your project on AWS using the provided command.

### Examples
#### Run latest version of code
```bash
$ floyd run "python train_tf.py -lr 0.01 -output /output/model.bin"
```

---------------------------------

## floyd logs

### Description
Display the logs of a run of your project

### Usage
```bash
floyd logs [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL for accessing logs in browser    |
| ID |      | ID of your job    |

### Extended Description
Display the logs of a run of your project

### Examples
#### Login using your username
```bash
$ floyd logs qYPdvbE5KS3TwANJFZdame
```

---------------------------------

## floyd output

### Description
Shows the output url of the run

### Usage
```bash
floyd output [OPTIONS] ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--url`, `-u` |      | Only print the URL for accessing logs in browser    |
| ID |      | ID of your job    |

### Extended Description
Shows the output url of the run. By default opens the output page in your 
default browser

### Examples
#### View the output dir of project with id qYPdvbE5KS3TwANJFZdame
```bash
$ floyd output qYPdvbE5KS3TwANJFZdame
# This will open the output dir link in browser
```

---------------------------------

## floyd status

### Description
Shows the status of your jobs

### Usage
```bash
floyd status [ID]
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job    |

### Extended Description
Shows the status of a run, if the ID is specified. It can also list the status of all 
the runs in the project

### Examples
#### View the status of all runs of current project
```bash
$ floyd ps
```

#### View the status of particular run
```bash
$ floyd ps qYPdvbE5KS3TwANJFZdame
```

---------------------------------

## floyd stop

### Description
Stop a run before it finishes

### Usage
```bash
floyd statop ID
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| ID |      | ID of your job    |

### Extended Description
Stop a run before it finishes

### Examples
#### Stop a run by ID
```bash
$ floyd stop qYPdvbE5KS3TwANJFZdame
```
---------------------------------