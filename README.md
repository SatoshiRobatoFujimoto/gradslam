> We are adding a few final touches, and this repo should be _stable_ shortly!

![](assets/gradslam-banner.png)

--------------------------------------------------------------------------------
gradSLAM is a fully differentiable dense SLAM framework. It provides a repository of differentiable building blocks for a dense SLAM system, such as differentiable nonlinear least squares solvers, differentiable ICP (iterative closest point) techniques, differentiable raycasting modules, and differentiable mapping/fusion blocks. One can use these blocks to construct SLAM systems that allow gradients to flow all the way from the outputs of the system (map, trajectory) to the inputs (raw color/depth images, parameters, calibration, etc.).

[![MITLicense](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT) [![CircleCI](https://circleci.com/gh/gradslam/gradslam.svg?style=shield&circle-token=109c43f395121b987111c85a9cf51d5fd75ea72c)](https://circleci.com/gh/gradslam/gradslam/tree/master) [![Docs](https://readthedocs.org/projects/gradslam/badge/?version=latest)](https://gradslam.readthedocs.io/en/latest/?badge=latest)


<p align="center">
	<img src="assets/pointfusiondemo.gif" />
</p> 


- [Overview](#overview)
- [Installation](#installation)
- Tutorials
- [Online Documentation](https://gradslam.readthedocs.io/en/latest/)
- Contributing to GradSLAM (coming soon)


## Overview

```python
rgbdimages = RGBDImages(colors, depths, intrinsics)
slam = PointFusion()
pointclouds, recovered_poses = slam(rgbdimages)
pointclouds.plotly(0).show()
```
Coming soon: a short demo


## Installation

### Requirements
- PyTorch >= 1.6.0

### Using pip (not functional yet)

`pip install gradslam`

### Install from GitHub

`pip install 'git+https://github.com/gradslam/gradslam.git'`

### Install from local clone (Recommended)

```
git clone https://github.com/gradslam/gradslam.git
cd gradslam
pip install -e .
```


## Building the package

In a `conda` environment (or a `virtualenv` environment if you prefer), install PyTorch (version `1.6.0` or greater). Then, `gradslam` can be installed by navigating into the base directory of this repo (i.e., the directory containing this readme file) and executing the following command.

```bash
python setup.py build develop
```

## Verifying the installation

To verify if `gradslam` has successfully been built, fire up the python interpreter, and import!

```py
import gradslam as gs
print(gs.__version__)
```

You should see the version number displayed.


## Running the unittests

From the base directory of the repo, run the following command.

```bash
pytest tests/
```

### Get coverage info

To get stats (in particular test coverage ratio), run

```bash
pytest test/ --cov
```

## Build docs (work-in-progress)

To build sphinx documentation, execute the following commands (**AFTER** building the `gradslam` package).

```bash
cd docs
sphinx-build . _build
```

This should build the docs in `docs/_build`. Open `docs/_build/index.html` in your web browser to access the docs.


## Citing gradslam

If you find `gradslam` useful in your work, and are writing up a report/paper about us, we'd appreciate if you cited us. Please use the following bibtex entry.

```
@inproceedings{gradslam,
  title={gradSLAM: Dense SLAM meets automatic differentiation},
  author={{Krishna Murthy}, Jatavallabhula and Saryazdi, Soroush and Iyer, Ganesh and Paull, Liam},
  booktitle={arXiv},
  year={2020},
}
```


## Contributors

* Soroush Saryazdi
* Krishna Murthy Jatavallabhula
* Ganesh Iyer
