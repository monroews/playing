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
