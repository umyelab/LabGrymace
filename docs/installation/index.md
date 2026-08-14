# Installation

Every setup installs two commands: **`LabGrymace`** (the pain tool) and **`LabGym_LabGrymace`** (our modified LabGym build).

**If you already have the original LabGym installed, it is safe to install LabGym_LabGrymace.** The modified build uses a different package name and command, so it will not overwrite or replace your existing LabGym installation. Both versions can coexist on the same computer.

```{important}
The `LabGym_LabGrymace` build is required — not optional. LabGrymace reads output generated only by this modified LabGym 2.9.0 build. The latest `LabGym` (v3.x) is **not compatible**. Because the two packages have different names, they can be installed side by side. See [How LabGym_LabGrymace differs from the original LabGym](https://github.com/devindwj0304/LabGrymace/blob/main/docs/LABGYM_CHANGES.md).
```

Requires **Python 3.10**.

If Anaconda or Miniconda is installed, run `conda deactivate` first so the install does not go into the conda base environment. LabGrymace pins specific versions of TensorFlow and NumPy that could otherwise downgrade packages in a shared environment.

Install **Python 3.10** from <https://www.python.org/downloads/>, then follow the steps for your system. The steps use the same method as the upstream [LabGym installation](https://labgym.readthedocs.io/en/latest/installation/index.html), but install the modified `LabGym_LabGrymace` build from this repository (`pip install ./LabGym_LabGrymace`), not the upstream LabGym release from PyPI.

```{toctree}
:maxdepth: 1

windows
macos
linux
usage
```

## Pretrained Models

LabGrymace requires two pretrained models, both available from the [LabGym Zoo](https://github.com/umyelab/LabGym/blob/master/LabGym_Zoo.md):

- the Detector `2026.4.6 detector Facial expression`, which tracks the ear, eye, and nose regions.
- the Categorizer `LabGrymace_categorizer`, which classifies the facial-region states used to compute the pain score.

After downloading the models:

- place the Detector in `LabGym_LabGrymace/LabGym_LabGrymace_copy/detectors/`
- place the Categorizer in `LabGym_LabGrymace/LabGym_LabGrymace_copy/models/`

Then select the two models in the LabGym_LabGrymace GUI.
