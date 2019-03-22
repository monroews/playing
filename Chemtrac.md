What is this

```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
Q = 75 * u.mL/u.min
w = 0.75 * u.mm
V= (Q/w**2).to(u.m/u.s)
V
Q_total = (500 * u.mL/u.min).to(u.mL/u.s)
Q_total
ConcAl = 1 * u.mg/u.L
ConcClay = 10 * u.NTU
(fm.sep_dist_clay(ConcClay,fm.Clay)**3).to(u.mm**3)

d_laser = 175 * u.um
A_laser = pc.area_circle(d_laser)
Guessed_sample_volume = (w*A_laser).to(u.mm**3)
Guessed_sample_volume
coag = 'PACl'
fm.Clay
DIM_FRACTAL = 2.3
VelTerm = 0.12 * u.mm/u.s
Temp = 20 * u.degC
floc_D = (fm.diam_floc_vel_term(ConcAl, ConcClay, fm.PACl, fm.Clay, DIM_FRACTAL, VelTerm, Temp)).to(u.um)
floc_D
fm.ener_dis_diam_floc(floc_D)
G = (np.sqrt(fm.ener_dis_diam_floc(floc_D)/pc.viscosity_kinematic(Temp))).to(u.Hz)
G

Re_flow_cell = (V*w/pc.viscosity_kinematic(Temp)).to(u.dimensionless)
Re_flow_cell

G_wall =( 8 * V/w).to(u.Hz)
G_wall
```
It seems likely that flocs in the core of the flow aren't sheared assuming that the viscous boundary layer is still developing.
Presumably the Chemtrac would detect a sheared floc as one particle if it creates a continuous signal.
