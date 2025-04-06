# 1_The_Basic_Tools_of_the_Deep_Life_Sciences
Fixing the Numpy Binary Compatibility Issue

# Running the previous version of the Colab notebook the following cell threw up an error :

import deepchem as dc
dc.__version__

# The error is shown below:

exact error message is:AttributeError                            Traceback (most recent call last)
<ipython-input-4-bd2c2b79eb3f> in <cell line: 0>()
----> 1 import deepchem as dc
      2 
      3 tasks, datasets, transformers = dc.molnet.load_tox21(featurizer='GraphConv')
      4 train_dataset, valid_dataset, test_dataset = datasets

20 frames
/usr/local/lib/python3.11/dist-packages/numpy/__init__.py in __getattr__(attr)
    309             return Tester
    310 
--> 311         raise AttributeError("module {!r} has no attribute "
    312                              "{!r}".format(__name__, attr))
    313 

AttributeError: module 'numpy' has no attribute 'dtypes'


# Reason for Error

The error was caused by an incompatibility between DeepChem and the latest NumPy version

# Fixing the Error 
The error was fixed by installing compatible versions as shown below 

# Install known compatible versions
%pip install numpy==1.23.5
%pip install tensorflow==2.12.0
%pip install --pre deepchem
%pip install rdkit-pypi



