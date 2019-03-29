```Python
import aguaclara
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
Q_Plant = 370 * u.mL/u.s
Tube_ID = 1/4 * u.inch   
head = 6*u.inch  
L = 1.5*u.m
Temp = 2*u.degC
K_minor=3
rough = aguaclara.core.materials.PVC_PIPE_ROUGH
nu = pc.viscosity_kinematic(Temp)
pc.flow_pipe
Q = (pc.flow_pipe(Tube_ID,head,L,nu,rough,K_minor)).to(u.L/u.s)
(Q/Q_Plant).to(u.dimensionless)

Floc_hopper_ID = 3*u.inch
Sludge_C = 28 * u.g/u.L
Raw_NTU = 100 * u.NTU  
Q_sludge = Raw_NTU * Q_Plant/Sludge_C
V_sludge = (Q_sludge/pc.area_circle(Floc_hopper_ID)).to(u.m/u.hr)
V_sludge

Up_V = 1 * u.mm/u.s
Sed_ID = 3 * u.ft
Sed_Q = (Up_V * pc.area_circle(Sed_ID)).to(u.L/u.s)
Sed_Q.to(u.L/u.day)

```
