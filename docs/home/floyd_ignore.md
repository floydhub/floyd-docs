Floydignore is a special floyd cli construct that allows you to specify 
which files need to be uploaded to the server. This is very similar to 
how gitignore works.

## Initialization

Everytime a new dataset or project is [initialized](../commands/init) using `floyd-cli` a new 
`.floydignore` file is created in the current path.

```bash
$ cd /code/project
$ floyd init style-transfer
Project "style-transfer" initialized in current directory
$ cat .floydignore

# Directories to ignore when uploading code to floyd
# Do not add a trailing slash for directories

.git
.eggs
eggs
lib
lib64
parts
sdist
var
```

Note: If a `.floydignore` file already exists in the initialization path, it will not be overridden.

## Options

There are different ways to specify files or directories that you want to be ignored. Below is 
a list with examples:

```
# Ignore all .dat files in the whole project:
*.dat

# Ignore all .dat files in some_folder:
/some_folder/*.dat

# Ignore all .dat files in some_folder and its subfolders:
/some_folder/**/*.dat

# Ignore all files (and folders) named .DS_Store
.DS_Store

# Ignore a specific file named .DS_Store located in some_folder
/some_folder/.DS_Store

# Ignore all files named .DS_Store in some_folder and its subfolders
/some_folder/**/.DS_Store

# Ignore all files in some_folder
/some_folder

# Ignore all files in some_folder (works the same as the rule above)
/some_folder/
```

Minimizing the number of files to upload saves upload time and disk space used 
by your experiments.

{!contributing.md!}
