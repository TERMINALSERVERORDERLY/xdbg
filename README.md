# xdbg

`xdbg` is an IPython extension that brings debugger features to the live coding environment. Works well with the IPython console, notebooks, and IPython-enabled text editors.

```pycon
In [1]: %load_ext xdbg

In [2]: def greeting():
   ...:     message = "Hello, world!"
   ...:     return msg
   ...:

In [3]: val = greeting()
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-3-3eb1da36ee89> in <module>()
----> 1 val = greeting()

<ipython-input-2-4f6ba759b8d0> in greeting()
      1 def greeting():
      2     message = "Hello, world!"
----> 3     return msg

NameError: name 'msg' is not defined

In [4]: %break greeting ?
1   def greeting():
2       message = "Hello, world!"
3       return msg


In [5]: %break greeting 3
New breakpoint 0

In [6]: val = greeting()
[xdbg] Entered: <__main__>.greeting

In [7]: message
Out[7]: 'Hello, world!'

In [8]: return message
[xdbg] Exited: <__main__>.greeting

In [10]: val
Out[10]: 'Hello, world!'
```

## Features

  * Set breakpoints and use the IPython REPL inside a function's scope
  * Move the REPL's scope into any imported module
  * Hotfix functions being debugged by specifying the correct behavior, instead of just watching them fail
  * Works well with text editor integration such as the [hydrogen package](https://github.com/nteract/hydrogen)
  for the Atom text editor

See http://kitaev.io/xdbg for more details.

## Installation

### Dependencies
* Python 3.5 or 3.6
* IPython

Note that older versions of Python are not supported.

### To Install

Run `pip install git+https://github.com/nikitakit/xdbg` (or clone the repository and use `setup.py`)

You can activate `xdbg` inside an IPython kernel by running `%load_ext xdbg`. To load it automatically,
list it in your IPython configuration file, e.g.

```python
c.InteractiveShellApp.extensions = ['xdbg']
```

The configuration file is usually located at `~/.ipython/profile_default/ipython_config.py`, and can be
generated by running `ipython profile create`.

## Documentation

For more details, see http://kitaev.io/xdbg
