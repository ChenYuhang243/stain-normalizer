# stain-normalizer
A GPU based color normalization method for  whole slide image(WSI) tiles, coded with cupy
# Install
`pip install stain-normalizer `
# How to Use
```python
from stain-normalizer import Normalizer    
normalizer = Normalizer()
normalizer.fit(template_tile)     
normalizer.normalize(target_tile)
```





  
