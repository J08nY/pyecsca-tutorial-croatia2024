# Setup

You have two options for getting ready for the tutorial:
 - Install several Python packages. [More info](#installing-everything-yourself)
 - Use [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/J08nY/pyecsca-tutorial-croatia2024/HEAD). [More info](#using-mybinder)

> [!NOTE]
> We recommend installing things yourself as myBinder has some limitations
> with regards to memory (only 2GB) and runtime (times out after 10 minutes of inactivity).

Furthermore, please download the example trace sets:
 - All tracesets (preferred): [zip](https://neuromancer.sk/static/traces.zip) or [tar.gz](https://neuromancer.sk/static/traces.tar.gz)
 - Or individually:
   - [Traceset A](https://neuromancer.sk/static/traces_A.pickle) 
   - [Traceset B](https://neuromancer.sk/static/traces_B.pickle) 
   - [Traceset C](https://neuromancer.sk/static/traces_C.pickle)  
   - [Traceset D](https://neuromancer.sk/static/traces_D.pickle)  

## How do I know the setup is ready?

1. You have cloned this repository and have a virtualenv with the requirements installed in it.
2. You have downloaded the tracesets above and placed them into the `notebooks` diretory.
3. Run `python -m jupyter lab` in the virtualenv with the mentioned Python packages installed. Open the
   `notebooks/start.ipynb` notebook and run the first cell with the imports.
   No errors (especially import ones) should be produced. See [troubleshooting.md] if they are.
4. You can continue running the rest of the prepared cells and play with the toolkit to
   learn about some of its API.


### Jupyter Lab quickstart

If you have not worked with Jupyter Lab before,
 you can have a look at this [handy tutorial](https://justinbois.github.io/bootcamp/2020_fsri/lessons/l01_welcome.html#Launching-a-Jupyter-notebook),
 or at its [full documentation](https://jupyterlab.readthedocs.io/en/stable/user/interface.html).

For the purposes of this tutorial, you will mainly need to know how to run cells.
Either use the ![](notebooks/img/play.png) button or `Shift + Enter` to run the current cell and move to the next one.

Make sure that you save your work (`Ctrl + S`) occasionally.

You can use tab-completion to learn about the attributes or methods of an object.

By typing `object?` you will get a help message with documentation of the object/function/class/method, same
goes for `object.method?` or `class.method?`.

## Installing everything yourself

You will need a Python environment to run the code during the tutorial.

### Python stuff

`python >= 3.9` and installed dependencies from [requirements.txt](/requirements.txt), which
include [pyecsca](https://neuromancer.sk/pyecsca/).

You can find **known-good versions of the packages** in the [known.txt](/known.txt) file, which
you can use instead of the requirements file.

> [!WARNING]
> Python 3.12 is kind of new and may bring some issues with installing other packages, we do not recommend it.

#### Linux

Ideally, use a virtual environment:

```bash
python -m venv virt
. virt/bin/activate
pip install -r requirements.txt
```

Afterwards run:
```bash
python -m jupyter lab
```
to start Jupyter Lab.

#### Windows

Ideally, use a virtual environment:

```bat
python -m venv virt
.\virt\Scripts\activate
pip install -r requirements.txt
```

Afterwards run:
```bat
python -m jupyter lab
```
to start Jupyter Lab.

## Using MyBinder

Simply navigate to [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/J08nY/pyecsca-tutorial-croatia2024/HEAD)
and wait for the Jupyter lab interface to load.

> [!WARNING]
> myBinder times out after 10 minutes of inactivity. To prevent that, open a terminal session when the lab first loads.

Some exercises require you to download trace sets. To do this on MyBinder, use a terminal session
and download them using the `wget` command (i.e. `wget <URL>`).
