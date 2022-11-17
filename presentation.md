---
jupytext:
  formats: md:myst,ipynb
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.1
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

+++ {"slideshow": {"slide_type": "slide"}}

<center>

# A quick introduction to `numpy-tutorials`

### NumPy Newcomer's Hour | November 17th, 2022

#### Ross Barnowski --- [@rossbar](https://github.com/rossbar) on GitHub

</center>

+++ {"slideshow": {"slide_type": "slide"}}

# Let's start with a question...

+++ {"slideshow": {"slide_type": "fragment"}}

Does the world really need **MORE** NumPy tutorials?!

+++ {"slideshow": {"slide_type": "subslide"}}

![Google search results for "numpy tutorial"](_static/numpy_tutorial_search_screenshot.png)

+++ {"slideshow": {"slide_type": "slide"}}

# Challenges with tutorial material

+++ {"slideshow": {"slide_type": "fragment"}}

* Keeping things up-to-date
  - New library features, removed features

+++ {"slideshow": {"slide_type": "fragment"}}

* Best-practices
  - There are *many* ways to solve a problem or use a tool; how do you know
    the way you're learning is a *good* way to do it

+++ {"slideshow": {"slide_type": "subslide"}}

## Examples

Casting

```{code-cell}
import numpy as np
a = np.array([1.0, 5.2])
```

```{code-cell}
a.astype(np.float32)
```

```{code-cell}
a.astype(np.int)
```

+++ {"slideshow": {"slide_type": "subslide"}}

## Examples

Random number generation

```{code-cell}
np.random.random((1000, 1000))
```

+++ {"slideshow": {"slide_type": "fragment"}}

[New random API](https://numpy.org/devdocs/reference/random/new-or-different.html)
introduced in v1.17

```{code-cell}
rng = np.random.default_rng()
rng.random((1000, 1000))
```

+++ {"slideshow": {"slide_type": "subslide"}}

## Examples

Partitioning domains

```{code-cell}
a = np.arange(0, 5, 0.2)
a
```

+++ {"slideshow": {"slide_type": "fragment"}}

```{code-cell}
a = np.arange(1250, 1350.005, 0.005)
a[-1]
```

+++ {"slideshow": {"slide_type": "slide"}}

# How do we address these issues?

+++ {"slideshow": {"slide_type": "fragment"}}

Tutorials should be **continuously tested**; this helps ensure they are
up-to-date with removed code/changed behavior in the library.

+++ {"slideshow": {"slide_type": "fragment"}}

Tutorial material should undergo **code review** to ensure that they reflect
best-practices and are kept up-to-date with new features.

+++ {"slideshow": {"slide_type": "subslide"}}

Testing tutorials requires that the source material be easily **executable**.
 
+++ {"slideshow": {"slide_type": "fragment"}}

- $LaTeX$ + Python scripts for figures/analysis, embed results in the
  source documents.
  * Feature-rich and powerful
  * Steep learning curve, custom build system, etc.

+++ {"slideshow": {"slide_type": "fragment"}}

- [`sphinx-gallery`](https://sphinx-gallery.github.io/stable/index.html)
  * Sphinx extension, easy integration with existing documentation infrastructure
  * Specialized format a bit clunky for narrative text

+++ {"slideshow": {"slide_type": "fragment"}}

- **Jupyter notebooks!**
  * Explicitly designed for executable/interactive technical communication
  * Extremely wide adoption

+++ {"slideshow": {"slide_type": "subslide"}}

But what about code review...

+++ {"slideshow": {"slide_type": "fragment"}}

- JSON format of `.ipynb` files, intended for browsers not humans
  * Inconvenient for code review: diffs are cluttered, hard to separate
    content changes from metadata, etc.

+++ {"slideshow": {"slide_type": "fragment"}}

If only there were a text-based Jupyter notebook format...

+++ {"slideshow": {"slide_type": "slide"}}

# [Executable Books Project](https://executablebooks.org/en/latest/)

- Content written in Jupyter notebooks: familiar, executable, interactive
- Sphinx-based, same(-ish) workflow as the NumPy documentation
- Text-based notebooks fit right into the typical fork-clone-push-PR development
  workflow
  * Reviews on GitHub + CI/CD
- Can author content either in the notebook browser interface or via text editor
- Tutorials are *interactive* for users e.g. via binder or JupyterHub.
  * [Even more exciting developments re: interactivity on the horizon...](https://www.myst.tools/docs/mystjs)

+++ {"slideshow": {"slide_type": "slide"}}

Alright, enough background - let's dive in!
