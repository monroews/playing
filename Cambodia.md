```python

from aguaclara.core.units import unit_registry as u
from aguaclara.core import physchem as pc
import aguaclara
from aguaclara.core import utility as ut
from aguaclara.core import pipes as pipes
import numpy as np
import math
import matplotlib.pyplot as plt
Q_proposed = (400000*u.m**3/u.day).to(u.L/u.s)
Q_proposed
Cost_proposed = 350000000*u.USD
CostperL_proposed = (Cost_proposed/Q_proposed).to(u.USD/(u.L/u.s))
CostperL_proposed
