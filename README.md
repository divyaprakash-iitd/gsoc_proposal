Prerequisite

Download the [SU2_Dataminer](https://github.com/EvertBunschoten/SU2_DataMiner)
To avoid python module issues, I recommend to set up a conda environment, `environment.yml` file with the following contents file and then install it using the following command.

```bash
conda env update -f environment.yml
```

```
name: su2-env
channels:
  - defaults
  - conda-forge
dependencies:
  - python=3.11
  - numpy
  - pip
  - tqdm
  - matplotlib
  - scikit-learn
  - tensorflow
  - pyfiglet
  - mpi4py
  - swig
  - pip:
    - CoolProp
    - cantera
```


Downloaded SU2
Checkout the develop branch
./meson.py build -Denable-pywrapper=true -Denable-mlpcpp=true --prefix=/home/baadalvm/su2_develop/SU2

The MLCPP contains the code which handles the ML part of the simulation.

SU2 was installed with the following options.

Message: -------------------------------------------------------------------------
         |    ___ _   _ ___                                                      |
         |   / __| | | |_  )   Release 8.1.0 "Harrier"                           |
         |   \__ \ |_| |/ /                                                      |
         |   |___/\___//___|   Meson Configuration Summary                       |
         |                                                                       |
         -------------------------------------------------------------------------

         Option          Value
         ---------------------
         TecIO:          true
         CGNS:           true
         AD (reverse):   false
         AD (forward):   false
         Python Wrapper: true
         Intel-MKL:      false
         OpenBlas:       false
         PaStiX:         false
         Mixed Float:    false
         libROM:         false
         CoolProp:       false
         MLPCpp:         true

         Please be sure to add the $SU2_HOME and $SU2_RUN environment variables,
         and update your $PATH (and $PYTHONPATH if applicable) with $SU2_RUN

         Based on the input to this configuration, add these lines to your .bashrc file:

         export SU2_RUN=/home/baadalvm/su2_develop/SU2/bin
         export SU2_HOME=/home/baadalvm/su2_develop/SU2
         export PATH=$PATH:$SU2_RUN
         export PYTHONPATH=$PYTHONPATH:$SU2_RUN

         Use './ninja -C build install' to compile and install SU2

Message:  WARNING: If compilation fails with a message regarding "attempted static link of dynamic object", reconfigure with option -Dstatic-cgns-deps=true.
Build targets in project: 18

SU2 8.1.0 "Harrier"

  User defined options
    prefix          : /home/baadalvm/su2_develop/SU2
    enable-mlpcpp   : true
    enable-pywrapper: true

Found ninja-1.10.0.git at /home/baadalvm/su2_develop/SU2/ninja

```



