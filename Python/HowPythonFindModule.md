How python finds its modules

Strictly taken, a module is a single python file, while a package is a folder containing python files, accompanied by a (can be empty) file named __init__.py, to tell python it is a package to import modules from. In both cases, modules need their .py extension, but importing them is done without (see further below).

By default, Python looks for its modules and packages in $PYTHONPATH.

To find out what is included in $PYTHONPATH, run the following code in python (3):

import sys
print(sys.path)
How to add a directory

Occasionally

From within a python file, you can add path(s) occasionally to the default path by adding the following lines in the head section of your python application or script:

import sys
sys.path.insert(0, "/path/to/your/package_or_module")
For example:

if I have a folder: /home/myname/pythonfiles, and I want to import the file module_1.py, located in that directory, I add this to the head section of my code:

import sys
sys.path.insert(0, "/home/myname/pythonfiles")
And I can simply import the file module_1.py by:

import module_1
When I create a package and want to import module(s) from the package, I need to create a folder in $PYTHONPATH, containing the modules, accompanied by a (can be empty) file called __init__.py

For example:

To import from a package (folder) called my_package in /home/myname/pythonfiles , add the /home/myname/pythonfiles path to your $PYTHONPATH, like in example 1, and import the module called module_2.py (inside the package folder) simply with: `

from <packagename> import module_2
Adding directories to $PYTHONPATH permanently:

Add the following line to your ~/.profile file.

export PYTHONPATH=$PYTHONPATH:/path/you/want/to/add
Subdirectories

From within a package, subdirectories are not included just like that; you need to "chain" the directories. To import a module module_3.py, inside folder subfolder inside folder packagename:

import packagename.subfolder.module_3
Given the fact that all subfolders in the package include their own __init__.py file.

When a module is in the same directory as the script or application

There is no need to insert the path to a module when it is in the same directory as the script or application, it is automatically added.

Example:

If I have a folder, containing script.py and module.py, I can simply import the module by:

import module
