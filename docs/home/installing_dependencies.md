## Python Dependencies

Floyd uses pre-defined docker [environments](environments.md) to run your projects. 
These are fairly exhaustive and comes with common packages such as NumPy, SciPy, 
scikit-learn, OpenCV, etc. preinstalled.

If your code needs additional Python packages to be available at run time, you 
can add them to a `floyd_requirements.txt` file. This is a special file that 
will be read at runtime and the packages listed here will be installed before 
running your command. Note that this file has to be in the same directory where
the floyd commands are run from.

```bash
$ echo "Pillow" > floyd_requirements.txt
```
