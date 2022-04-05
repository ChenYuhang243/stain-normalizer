# stain-normalizer
A color normalization method for  whole slide image(WSI) tiles, using cupy and tiffile with GPU to accerate the process, which result in a at least 100X faster speed.

# How to install
`pip install stain-normalizer `
# Requirements
  1. cupy
  2. one GPU with according cuda installed
# How to use
```python
from stain-normalizer import Normalizer    
normalizer = Normalizer()
normalizer.fit(template_tile)     
normalizer.normalize(target_tile)
```
# Example Usage

# Suggestions
  1. use tifffile to load image
  2. use multi GPU. Cupy uses one GPU by default.
  3. Use LMDB or H5DF to load or save image. Or save as numpy format data ".npy". If use tensorflow, tfrecords is suggested. Single image format is least recommeded.
  4. Use multiprocessing or simply cut images into several chunks and run several jobs.
  
# Other implements
  1. pytorch implement: https://github.com/EIDOSlab/torchstain
  2. 
# Referrence
[1] Macenko, Marc, et al. "A method for normalizing histology slides for quantitative analysis." 2009 IEEE International Symposium on Biomedical Imaging: From Nano to Macro. IEEE, 2009.



  
