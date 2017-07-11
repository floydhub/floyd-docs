Floydignore is a special floyd cli construct that allows you to specify
which files need to be uploaded to the server. This is very similar to
how gitignore works.

Minimizing the number of files to upload saves upload time and disk space used
by your experiments.


## Initialization

Everytime a new dataset or project is [initialized](../commands/init) using `floyd-cli` a new
`.floydignore` file is created in the current path.

```bash
$ cd /code/project
$ floyd init style-transfer
Project "style-transfer" initialized in current directory
$ cat .floydignore

# Directories and files to ignore when uploading code to floyd

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

There are different ways to specify files, directories, or
[glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) that you want
to be ignored. Below is a list with examples:

```
# Ignore all .dat files in the whole project:
*.dat

# Ignore all .dat files in some_folder:
some_folder/*.dat

# Ignore all .dat files in some_folder and its subfolders:
some_folder/**/*.dat

# Ignore all files (and folders) named .DS_Store
.DS_Store

# Ignore a specific file named .DS_Store located in some_folder
some_folder/.DS_Store

# Ignore all files named .DS_Store in some_folder and its subfolders
some_folder/**/.DS_Store

# Ignore all files in some_folder
/some_folder/

# Ignore all files in some_folder (works the same as the rule above)
some_folder/

# Ignore all files in some_folder (works the same as the rule above)
some_folder
```

You can also whitelist files, directories, and glob patterns by preceding them
with a `!`.  Items matching the pattern following the `!` that were excluded by
a previous pattern will become included again. It is not possible to re-include
a file if a parent directory of that file is excluded. Put a backslash (`\`) in
front of the first `!` for patterns that begin with a literal `!`, for example,
`\!important!.txt`.

{!contributing.md!}
