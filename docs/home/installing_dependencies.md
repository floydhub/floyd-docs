## Python Dependencies

Floyd uses pre-defined docker [images](environments.md) to run your projects.
If your code needs additional Python packages to be available at run time, you 
can add them to a `floyd_requirements.txt` file. This is a special file that 
will be read at runtime and the packages listed here will be installed before 
running your command.

```bash
$ echo "Pillow" > floyd_requirements.txt
```
