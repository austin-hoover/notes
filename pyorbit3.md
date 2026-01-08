# PyORBIT3


## Compilation

Meson will automatically recompile. But if you want to start from scratch:

```
mkdir build
meson setup build
meson compile build
```


## Installation

```
conda install conda-forge::openmpi
pip install --no-build-isolation --editable .
```

## Linac tracking module

* The linac_tracking module differs from TEAPOT in two ways:
    * It is reversible.
    * It is not symplectic. (This is not expected to matter much in a single-pass linac.)
    * It computes transverse positions x using the particle z, not the synchronous particle z. This way, particles with large phases will not survive apertures artificially. (This is not a completely consistent approach, but I'm not sure of a better solution for s-based tracking.)


## Printing with MPI

Use `sys.stdout.flush()` after print statements, otherwise all print statements are delayed until the end of the end of the run.


## Reinstall command line
```
xcode-select -p
sudo rm -rf /Library/Developer/CommandLineTools
xcode-select --install
```


