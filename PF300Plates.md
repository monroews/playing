```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
Sed_D = 36*u.inch
Plate_angle = 60 * u.degree
Sed_long_D = Sed_D/np.sin(Plate_angle)
Sed_long_D
```
