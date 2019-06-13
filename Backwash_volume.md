# Backwash volume

```python

from aguaclara.core.units import unit_registry as u
from aguaclara.core import physchem as pc

from aguaclara.core import utility as ut
import numpy as np
import matplotlib.pyplot as plt

t_backwash = 15 * u.min  
t_runtime = 24 * u.hr   
Q_plant = 120 * u.L/u.s    
Q_backwash = (Q_plant * t_backwash/t_runtime).to(u.L/u.s)
Q_backwash
v_capture = 0.12 * u.mm/u.s
A_lagoon_settle = (Q_backwash/v_capture).to(u.m**2)
A_lagoon_settle
H_lagoon = 3 * u.m
t_lagoon = 10 * t_runtime
V_lagoon = t_lagoon * Q_backwash
A_lagoon = (V_lagoon/H_lagoon).to(u.m**2)
A_lagoon
L_Lagoon = np.sqrt(A_lagoon*4)
L_Lagoon
W_Lagoon = L_Lagoon/4
W_Lagoon
W_Lagoon*L_Lagoon
```
