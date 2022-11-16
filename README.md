# Intro to `numpy-tutorials` - NumPy Newcomer's Hour, Nov. 17th 2022

A brief presentation to kick off discussion around the `numpy-tutorials`
project.
The presentation is in the form of a
[text-based Jupyter notebook written in MyST markdown][myst-nb] and can be view
in presentation form via [RISE][RISE].

### Setup

To view the presentation locally you must install the dependencies.
Start by creating (if necessary) and entering a new Python environment:

```bash
python -m venv pres-env
source pres-env/bin/activate
```

The install the requirements:

```bash
python -m pip install -r requirements.txt
```

### Viewing the presentation

In the `pres-env` environment, launch Jupyter notebook and open `presentation.md`:

```bash
jupyter notebook presentation.md
```

From the notebook, you can enter/exit presentation mode with `alt+r`.
In presentation mode, use `<space>` to navigate to the next slide and
`<shift>+<space>` to move back.

Note that the slides look best when in fullscreen mode (toggle with `<F11>`).

[myst-nb]: https://myst-nb.readthedocs.io/en/latest/authoring/text-notebooks.html
[RISE]: https://rise.readthedocs.io/en/stable/
