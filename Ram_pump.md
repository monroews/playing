```python

from aguaclara.core.units import unit_registry as u
from aguaclara.core import physchem as pc

from aguaclara.core import utility as ut
import numpy as np
import math
import matplotlib.pyplot as plt
deltax=1*u.cm
Fspringmax = 4 * u.N
Mspringmax = (Fspringmax/u.gravity).to(u.kg)
Mspringmax
t_close = 0.1 * u.s
F_accelerate_mass = (2 * Mspringmax * deltax / t_close**2).to(u.N)
F_accelerate_mass
K_minor = 3
L_drive = 2 * u.m
t_water_accelerate = (math.atanh(0.9)/(u.gravity/(2*L_drive*K_minor))**(1/2)).to(u.s)
t_water_accelerate
```

$$t_{0.9 V_{f}}=\frac{\tanh ^{-1}(0.9)}{\sqrt{\frac{g H}{2 L^{2}}\left(\Sigma K+\mathrm{f} \frac{L}{D}\right)}}$$
