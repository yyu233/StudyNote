```if __name__ == "__main__":```

Python modules are just script files that are located in a place where Python can find them. As with all scripts, you can just run them directly if you know where they are, e.g. python /path/to/module.py.

Properly designed modules usually do nothing except set up stuff (e.g. functions and types you could import), but they usually won’t have any visible side effect. That’s why you can do import sys and nothing happens.

However, some modules may offer useful stuff when they are run from the command line. Examples for that include venv but also http.server or idlelib: All of those are regular modules that can be imported from other modules without side effects.

But when executed directly, they all do things (e.g. venv sets up a virtual environment, http.server runs a simple HTTP server, and idlelib runs IDLE). This is usually done with the following check:

if __name__ == '__main__':
    print('Module is being executed directly, so do stuff here')
This is a special way of recognizing of a script/module is being executed directly, or whether it’s just being imported from some other module. You can learn more about the question “What does if __name__ == '__main__': do?”.

So, you can run a module directly using python /path/to/module.py as we established before. But this requires you to know the full path to the module. That’s where the -m option comes into play: For modules that can usually be imported just using import modulename, you can use python -m modulename to run that module directly. Just as if you typed the full path to it.

So for our above examples, we can just use python -m venv, python -m http.server. or python -m idlelib.
