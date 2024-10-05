# stain-normalizer
A color normalization method for  whole slide image(WSI) tiles, using cupy and tiffile with GPU to accerate the process, which result in a at least 100X faster speed.

# Requirements
  1. cupy
  2. one GPU with according cuda installed
# How to use
```python
import tifffile as tif
from stain-normalizer import Normalizer  #if u copy StainNormalizer.py file in working directory
template_tile = tif.TiffSeqence(template_path).asarray() ## u can choose one or several template tiles, but make sure shape of template_tile is 4-D array
target_tile = tif.imread(target_tile_lists) ## return a 4-D array
normalizer = Normalizer()
normalizer.fit(template_tile)     
normalizer.normalize(target_tile) 
```
# Comparement
  * read 2000 tiles(512* 512 * 3) into numpy
    - tifffile.imread read: 1m17s
    - Image.open read: 9m38s
    - cv2.imread : 10m46s
  * color normalization 30k tiles with chunksize=100,V100(16G) without writing tiles to disk: 21m 46s.
# Suggestions
  1. use tifffile to load image
  2. use multi GPU. Cupy uses one GPU by default.
  3. Use LMDB or H5DF to load or save image. Or save as numpy format data ".npy". If use tensorflow, tfrecords is suggested. Single image format is least recommeded.
  4. Use multiprocessing or simply cut images into several chunks and run several jobs.

  
# Other implements
  1. pytorch implement: https://github.com/EIDOSlab/torchstain
  2. numpy: https://github.com/schaugf/HEnorm_python
  3. matlab: https://github.com/mitkovetta/staining-normalization
  4. python modules with different methods:https://github.com/Peter554/StainTools
  
# Referrence
[1] Macenko, Marc, et al. "A method for normalizing histology slides for quantitative analysis." 2009 IEEE International Symposium on Biomedical Imaging: From Nano to Macro. IEEE, 2009.



  
