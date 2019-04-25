```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np

ID = 1/4 * u.inch  
A_Pipe = pc.area_circle(ID)
(A_Pipe*4*u.inch/(10*u.s)).to(u.L/u.min)
199/4500
159/3000
99/1200
15/200
20/300
25/500
35/750
50/750
125/1500
(4* u.Mgal/u.day/3).to(u.L/u.s)
(37.6*u.MUSD/(4* u.Mgal/u.day)).to(u.kUSD/(u.L/u.s))
```
