# stain-normalizer
A color normalization method for  whole slide image(WSI) tiles, using cupy and tiffile with GPU to accerate the process, which result in a at least 100X faster speed.
# How to install
`pip install stain-normalizer `
# How to use
```python
from stain-normalizer import Normalizer    
normalizer = Normalizer()
normalizer.fit(template_tile)     
normalizer.normalize(target_tile)
```





  
