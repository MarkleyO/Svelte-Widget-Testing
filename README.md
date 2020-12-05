# Svelte Widget and Jupyter Notebook

Start of our widget for Jupyter (this was built off the foundation of the repo
  https://github.com/cabreraalex/widget-svelte-example)

## Installation

*I had a little bit of trouble trying to get the initial project installed and
running using standard Jupyter so I would reccommend following the JupyterLab
installation instructions*

*Also I'm hoping to change the name of this repo/project soon, so I'll update
the instructions in this Markdown file to match that soon.*

You can install using `pip`:

```bash
pip install widget_svelte_example
```

Or if you use jupyterlab:

```bash
pip install widget_svelte_example
jupyter labextension install @jupyter-widgets/jupyterlab-manager
```

I doubt that any of us have Jupyter Notebook 5.2 or earlier, but if anyone does you
would likely need to enable the nbextension:

```bash
jupyter nbextension enable --py [--sys-prefix|--user|--system] widget_svelte_example
```

## Development Installation

```bash
# First install the python package. This will also build the JS packages.
pip install -e .
```

We need to manually enable our extensions with the notebook / lab frontend:

```
jupyter labextension install @jupyter-widgets/jupyterlab-manager --no-build
jupyter labextension install .
```

For classic notebook, you can run, but again, I was unable to get this to work:

```
jupyter nbextension install --sys-prefix --symlink --overwrite --py widget_svelte_example
jupyter nbextension enable --sys-prefix --py widget_svelte_example
```

*I'm not running on windows, but if you are these additional instructions were
included:*

Note that the `--symlink` flag doesn't work on Windows, so you will here have to run
the `install` command every time that you rebuild your extension. For certain installations
you might also need another flag instead of `--sys-prefix`, but we won't cover the meaning
of those flags here.

### Developing and Monitoring Changes

#### Typescript:

To continuously monitor the project for changes and automatically trigger a rebuild, start Jupyter in watch mode:

```bash
jupyter lab --watch
```

And in a separate session, begin watching the source directory for changes:

```bash
npm run watch
```

After a change wait for the build to finish and then refresh your browser and the changes should take effect.

#### Python:

If you make a change to the python code then you will need to restart the notebook kernel to have it take effect.


## Owen's Notes:

I've been using Conda to manage my python packages. In order to set this up, I
followed the installation instructions for miniconda on:
https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html.

I then created a new environment using:

```bash
conda create --name widget-env
```

This can be activated or deactivated using
```bash
conda activate widget-env
```
or
```bash
conda deactivate
```
Once this environment is set up, install libraries as follows:
```bash
conda install numpy
```

Hopefully this works! Let me know if something doesn't.

### Important Documentation and Helpful Tutorials:

#### JupyterLab Examples and Resources:
* [Creating Reactive Jupyter Widgets With Svelte Tutorial](https://cabreraalex.medium.com/creating-reactive-jupyter-widgets-with-svelte-ef2fb580c05)
* [Starting Example](https://github.com/cabreraalex/widget-svelte-example)
* [JupyterLab Extension Astronomy Example](https://jupyterlab.readthedocs.io/en/stable/developer/extension_tutorial.html)

#### Library Resources:
* [Svelte API](https://svelte.dev/docs#get)
* [HTML Canvas w3schools](https://www.w3schools.com/html/html5_canvas.asp)
* [HTML / JS Canvas w3resource](https://www.w3resource.com/javascript-exercises/javascript-drawing-exercise-2.php)
