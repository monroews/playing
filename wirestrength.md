# Checking the wire strength of very small diameter wire

```python

from aguaclara.core.units import unit_registry as u
from aguaclara.core import physchem as pc

from aguaclara.core import utility as ut
import numpy as np
import matplotlib.pyplot as plt
D_wire = 0.032 * u.inch
Tensile = 70000 * u.psi
elasticity = 200 * u.GPa
A_wire = np.pi * D_wire**2/4
Wire_strength = (A_wire*Tensile).to(u.N)
Wire_strength
Stress = 1 * u.kg * u.standard_gravity/A_wire
Strain = (Stress/elasticity).to(u.dimensionless)
print('The wire will stretch',(Strain*4*u.m).to(u.mm),'when the force changes by 1 kg')
```
