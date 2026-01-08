# PyORBIT2

## Install on Mac M1 chip

Create python2.7 conda environment
https://stackoverflow.com/questions/67380286/anaconda-channel-for-installing-python-2-7
```
CONDA_SUBDIR=osx-64 conda create --name=pyorbit2 python=2.7
conda activate pyorbit2
conda config --env --set subdir osx-64
```

Install MPICH and FFTW
```
conda install conda-forge::mpich
conda install conda-forge::fftw
```

Install clang++ compiler
```
conda install -c conda-forge cxx-compiler
```

Add line to /conf/make_root_config. (C++17 gives error for "register" command https://en.cppreference.com/w/cpp/language/storage_duration.)
```
CXXFLAGS += -std=gnu++14
```

Compile:
```
make
```

