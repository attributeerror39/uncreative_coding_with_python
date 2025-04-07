# Setup environment

## Python

[Python](https://www.python.org/) is an easy to write general purpose programming language, meaning it can be used for a variety of different applications.

## Scripting language

Python is a [scripting language](https://www.wikiwand.com/en/Scripting_language). Code written in Python is interpreted on the fly, instead of compiled into a piece of software beforehand.
Python can be used to write stand-alone software, but (as other scripting languages) it can also be used to extend the functionality of existing software.

For example Python scripts can extend 

- Blender
- Grasshopper
- GIMP
- FontForge
- Glyphs

## Terminal 

As a scripting language Python can be used inside the console (Command Line Interface) of your OS in an **interactive** mode: type a line of code, press enter and it's interpreted.

![terminal](img/terminal.png)

```
~$ python3
Python 3.10.6 (main, Mar 10 2023, 10:55:28) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import numpy as np
>>> import matplotlib.pyplot as plt
>>> data = np.random.randint(low=0, high=2, size=(7,7), dtype=int)
>>> plt.imshow(data)
<matplotlib.image.AxesImage object at 0x7f051108bd90>
>>> plt.show()
```
(The `$` is an indicator for code that's written in the CLI. If you see `>>>` before Python code, this means that it's written in an interactive session.)

Code is nothing else then plain text. The code above (without `>>>`)

```python
import numpy as np
import matplotlib.pyplot as plt
data = np.random.randint(low=0, high=2, size=(7,7), dtype=int)
plt.imshow(data)
plt.show()
```
written to a file like `random7x7.py` can be executed through the CLI:

`$ python random7x7.py`

## Virtual environment

It is recommended to create a virtual environment for your project/ setup. All the libraries and dependencies installed for this project are isolated and won't conflict other libraries and their dependencies. The easiest way to create a virtual environment may be with **conda**, but other options like **pipenv** are also possible. We will work with Anaconda or Miniconda.

[Anaconda or Miniconda?](https://docs.conda.io/projects/conda/en/latest/user-guide/install/download.html#anaconda-or-miniconda) 

The main difference is that Anaconda has a GUI to manage/ start environments. In addition more libraries are installed than with miniconda. Miniconda is controlled through the CLI, which may be faster and is definitely lighter. 

### Anaconda

[Download](https://www.anaconda.com/download) and install Anaconda. Next to Python, a GUI (Anaconda Navigator) to manage packages and environments is included.

Open Anaconda Navigator

Click on `Environemnts` in the left pane, then click `create`

Type a name, like `fpdf2` and the environment will be created

Click on the `play` button right to the environment, open a terminal and type

`pip install flat`

Then click on `Home`, then you see a grid of Applications: `Install` Jupyter Lab.

Then start Jupyter Lab, a browser window should open. On the left is a file explorer, where you can search for the project folder. Try to run the notebook.

### Miniconda

[Download](https://docs.conda.io/en/latest/miniconda.html) Miniconda3 for your OS and execute the installer. Miniconda includes Python.

Open the command line of your operating system (see help for [Linux](https://www.wikihow.com/Open-a-Terminal-Window-in-Ubuntu), [Mac](https://www.wikihow.com/Open-a-Terminal-Window-in-Mac), ([Windows](https://www.wikihow.com/Open-Terminal-in-Windows)) (for Windows users: open "Anaconda Prompt") and create a new environment. Type the following line by line and press <code>Enter</code> after each line.

``` shell
# check if conda is installed
conda --version
```

#### Create a new environment

Change the name `my_environment` in the code below to a name of your choice. (It's common that variable values inside code snippets are enclosed by `<` and `>`, like below. If so, replace the name *inclusive* `< >` with a name of your choice.) This is the name of your environment and you have to type it when you start it later on, so make sure it's not too long and easy to remember.

``` shell
# create a new environment with Python version 3.12
conda create -n <my_environment> python=3.12 -y
# for example: conda create -n uncreativepython python=3.12 -y
```

You can see all environments created by you with the following command:

```shell
# list available environments
conda env list
```

Next we can activate our newly created environment. (Of course you have to insert your environments name in the place of `<my_environment>`.)

```shell
# activate your environment
conda activate <my_environment>
```

### Install external packages with pip

We can use Python's package installer **pip** to install external libraries like [fpdf2](https://pypi.org/project/fpdf2/).

```shell
# important: activate your environment first
conda activate <my_environment>

# install the library fpdf2 with pip
pip install fpdf2
```

## Deactivate conda

When we've finished our work, we can deactivate the environment with:

```shell
# deactivate environment
conda deactivate
```

## Remove an environment

```shell
conda remove -n <my environment> --all
```

## Appendix

### Terminal emulators 

Here are some terminal emulators (beyond the default one of your OS):

**Cross Platform**

[Alacritty](https://alacritty.org/)

[Kitty](https://sw.kovidgoyal.net/kitty/)

[Tabby](https://tabby.sh/) 

**Linux**

[Terminator](https://gnome-terminator.org/)

[Konsole](https://konsole.kde.org/)

**Mac**

[iTerm2](https://iterm2.com/)
