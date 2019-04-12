```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
D= 5 * u.inch
density = 150 * u.lb/u.ft**3
density.to(u.kg/u.m**3)
V = 4 * u.ft/u.s   
nu_dynamic = 100000 * u.centipoise

Re = (V*D *density/(nu)).to(u.dimensionless)
Re

Q= (V*pc.area_circle(D)).to(u.yard**3/u.min)
Q
nu_kinematic = (nu_dynamic/density).to(u.mm**2/u.s)
nu_kinematic
f=64/Re
f
L = 600 * u.ft
Rough = 0*u.mm
Kminor=10
pc.headloss(Q,D,L,nu_kinematic,Rough,Kminor)
