[![Project Status](https://img.shields.io/pypi/status/kalmus.svg)](https://pypi.org/project/kalmus/)
[![Python Version](https://img.shields.io/pypi/pyversions/kalmus.svg)](https://pypi.org/project/kalmus/)
[![PyPI Version](https://img.shields.io/pypi/v/kalmus.svg)](https://pypi.org/project/kalmus/)
[![codecov](https://codecov.io/gh/KALMUS-Color-Toolkit/KALMUS/branch/master/graph/badge.svg)](https://codecov.io/gh/KALMUS-Color-Toolkit/KALMUS)
[![License](https://img.shields.io/pypi/l/kalmus.svg)](https://pypi.org/project/kalmus/)
[![codecov workflow](https://github.com/KALMUS-Color-Toolkit/KALMUS/actions/workflows/test-codecov.yml/badge.svg)](https://github.com/KALMUS-Color-Toolkit/KALMUS/actions/workflows/test-codecov.yml)
[![build workflow](https://github.com/KALMUS-Color-Toolkit/KALMUS/actions/workflows/python-package.yml/badge.svg)](https://github.com/KALMUS-Color-Toolkit/KALMUS/actions/workflows/python-package.yml)

# KALMUS

KALMUS is a Python package for the computational analysis of colors in films. 
It provides quantitative tools to study and compare the use of film color. 
This package serves two purposes: (1) various ways to measure, calculate and compare a film's colors 
and (2) various ways to visualize a film's color. We have named the software KALMUS in homage to 
Natalie Kalmus (1882 - 1965), a Technicolor Director who oversaw the color palettes of nearly 300 
Hollywood feature films.

KALMUS utilizes the movie barcode as a visualization of the film's color. It has a modularized pipeline for the
 generation of barcodes using different measures of color and region of interest in each film frame. KALMUS provides
 a low-level API, high-level command line, and Graphic user interface for audience from all backgrounds to take
 advantage of its functionality. 

- What is a Movie Barcode: [KALMUS: tools for color analysis of films](paper/joss-paper.md)   
- How do I install the KALMUS: [KALMUS Installation Guide](https://kalmus-color-toolkit.github.io/KALMUS/install.html) 
and [KALMUS PyPI Homepage](https://pypi.org/project/kalmus/).
- How do I use the KALMUS: [Notebook Tutorials for KALMUS's API, GUI, and CLI](notebooks)
- How do I contribute to the KALMUS: [KALMUS Contribution Guidelines](CONTRIBUTING.md)
- How do I run the KALMUS's automated test suite: [Auomated Test Suite](tests/)

**Examples of Barcode visualization:**

<p align="center">
  <img width="" height="" src="notebooks/notebook_figures/mission_barcode_whole_frame_avg.png">
  <br>Figure 1. Mission: Impossible (1996) color barcode using the average color of whole frame for each frame</br>
  <br>
  <img width="" height="" src="notebooks/notebook_figures/mission_barcode_Foreground_avg.png">
  <br>Figure 2. Mission: Impossible (1996) color barcode using the average color of foreground of each frame</br>
</p>

# API Documentation

The KALMUS API reference is now available on 
[https://kalmus-color-toolkit.github.io/KALMUS/kalmus.html](https://kalmus-color-toolkit.github.io/KALMUS/kalmus.html).

# Installation Guide

The kalmus package requires a python with version 3.7 or 3.8.

The package is released on PyPI ([Project Homepage](https://pypi.org/project/kalmus/)). After you installed the
python==3.7, 3.8, you can install the kalmus using pip (recommended)

    $ pip install kalmus


Alternatively, you could install the kalmus locally by first cloning this GitHub repo.
Then, move to the top directory of cloned kalmus project folder and install using the pip command

    $ pip install .

In both methods, the package's dependencies will be automatically installed. You can verify if the kalmus has been
installed in your environment using the pip command

    $ pip show kalmus

Alternatively, in version 1.3.7 and above, you can check the version of installed kalmus using its 
`.__version__` attribute.

```jupyter
>>> import kalmus
>>> print(kalmus.__version__) # Warning: The __version__ attribute is not available in the kalmus v.1.3.6 and backward
>>> 1.3.7 
```

## For users with Apple M1 Chip (arm64 Architecture)

As @elektrobohemian mentioned in [issue #4](https://github.com/KALMUS-Color-Toolkit/KALMUS/issues/4), you may experience installation errors when using pip to install kalmus's dependencies, such as scikit-image, scikit-learn, scipy, and numpy. To resolve this issue, you need to install the kalmus's dependencies through [Miniforge](https://github.com/conda-forge/miniforge), a conda-forge maintained minimalistic conda installer. You can download and install the Miniforge for OS X system with M1 processor (arm64 Architecture) on [Miniforge's GitHub Page](https://github.com/conda-forge/miniforge#download) or click this [Download link](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh).

**Instructions (tentative):**

* After installing the **Miniforge**, please open a terminal and create a python virtual environment through conda:
```
$ conda create -n your_env_name python=3.7
```

* Activate the virtual environment:
```
$ conda activate your_env_name
``` 

* Install the kalmus's dependencies through conda (the installed packages come from the conda-forge channel):
```
$ conda install numpy
$ conda install opencv
$ conda install matplotlib
$ conda install scipy
$ conda install pandas
$ conda install biopython
$ conda install kiwisolver
$ conda install scikit-learn
$ conda install scikit-image
```

* Last step, install the kalmus through pip in your virtual environment:
```
$ pip install kalmus
```

This is a tentative approach to resolve the installation issues on machines with arm64 Architecture. If the instructions above does not solve your problem or you are experiencing other difficulties, please open an [issue](https://github.com/KALMUS-Color-Toolkit/KALMUS/issues) of your problems in this GitHub repo.

# Get Started

KALMUS has a low-level API, high-level command line, and Graphic user interface for audience from all 
backgrounds to take advantage of its functionality. 

To get started on KALMUS, we encourage you to check the Jupyter notebook tutorials in the [notebooks](notebooks) 
folder. We provide the interactive notebook tutorials for users to get started on KALMUS using its API, GUI, and CLI. 
Notice that the Command-line interface (CLI) is only available in KALMUS v1.3.7 or onward.

- [Notebook Tutorial for Graphic User Interface](notebooks/user_guide_for_kalmus_gui.ipynb)
- [Markdown Tutorial for Graphic User Interface](notebooks/USAGE_GRAPHIC_USER_INTERFACE.md)
- [Notebook Tutorial for Application Programming Interface](notebooks/user_guide_for_kalmus_api.ipynb)
- [Markdown Tutorial for Command-line interface](notebooks/USAGE_COMMAND_LINE_UI.md)
- [Notebook Tutorial for Advanced API Usage](notebooks/advanced_guide_for_kalmus_api.ipynb)

# Contribution

We encourage contributions, including bug fixes and new features, from our community users. When contributing to the 
kalmus package, please contact the project maintainers by email <yc015@bucknell.edu> or opening an issue. If 
your bug fixes or new features change the current behaviors of package, please specify the changes and reasons in the 
discussion with project maintainers. 

We encourage inclusive and friendly discussion. Please follow our [code of conduct](CODE_OF_CONDUCT.md) when 
communicating. 

# Test Suite

We provide an [automated test suite](tests/) that covers the core functionality of KALMUS. Before running the automated test suite locally, 
make sure you have installed the latest versions of [pytest](https://pypi.org/project/pytest/), [pytest-cov](https://pypi.org/project/pytest-cov/), 
and [kalmus](https://pypi.org/project/kalmus/), and you have cloned the project repository on master branch. 

To run the test suite:  
- Go to the top directory of cloned KALMUS project
- Use command `$ python -m pytest tests --cov=kalmus --cov-config=.coveragerc --cov-report term-missing`

See the [Test Suite Guide](tests/README.md) for more details.

# Acknowledgment

The authors wish to thank the Mellon Foundation, the Dalal Family Foundation, and the Bucknell University Humanities 
Center for their support on this project. The project is released under the open-source MIT License.

# Update Log

The full update log (from [v1.3.0](https://pypi.org/project/kalmus/1.3.0/) to [v1.3.8](https://pypi.org/project/kalmus/)) 
is now available on [https://kalmus-color-toolkit.github.io/KALMUS/update_log.html](https://kalmus-color-toolkit.github.io/KALMUS/update_log.html)
