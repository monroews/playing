```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
v_bw = 11 * u.mm/u.s
N_outlets = 3
w = 10 * u.cm
Q_outlet = (v_bw*w**2/N_outlets).to(u.mL/u.s)
print('The flow rate through one filter outlet is', ut.round_sf(Q_outlet,2))
tubing18 = 3.8 * u.mL/u.revolution
Maxspeed = 600 * u.revolution/u.min
Q_pump_max = (Maxspeed * tubing18).to(u.mL/u.s)
print('The max flow rate with one peristaltic pump is', ut.round_sf(Q_pump_max,2))
#What is the max flow from a peristaltic pump with #18 tubing at 600 rpm?

```

See [CEE 4530 lab manual on pumps](https://monroews.github.io/EnvEngLabTextbook/Acid_Rain/Acid_Rain.html#id3) to see
