```python

from aguaclara.core.units import unit_registry as u
from aguaclara.core import physchem as pc
import aguaclara
from aguaclara.core import utility as ut
from aguaclara.core import pipes as pipes
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
K_minor = 4
L_drive = 1.74 * u.m
t_water_accelerate = (math.atanh(0.7)/(u.gravity/(2*L_drive*K_minor))**(1/2)).to(u.s)
t_water_accelerate

t_pressurewave = 150 * u.ms
a_celerity = (4*L_drive/t_pressurewave).to(u.m/u.s)
a_celerity

#theoretical wave velocity
D_pipe = pipes.ID_sch40(1*u.inch)
t_pipe = (pipes.OD(1*u.inch)-D_pipe)/2
K = 2.2 * u.GPa
E = 2.4*u.GPa
a_celerity_theory = (np.sqrt((K/pc.density_water(20*u.degC))/(1 + K/E * D_pipe/t_pipe))).to(u.m/u.s)
a_celerity_theory

v_final = (np.sqrt(2*u.gravity*L_drive/K_minor)).to(u.m/u.s)
v_final
H_pump = 6*u.m
t_water_decelerate =( v_final/u.gravity*L_drive/H_pump).to(u.s)
t_water_decelerate
Volume_Cycle = (pc.area_circle(D_pipe)*v_final**2/2/u.gravity * L_drive/H_pump).to(u.mL)
Volume_Cycle

QRampump = Volume_Cycle/t_water_accelerate*0.1
QRampump
Q_PlantMax = (QRampump*10000).to(u.L/u.s)/3
Q_PlantMax
(60*u.psi/(pc.density_water(20*u.degC)*u.gravity)).to(u.m)
```

$$t_{0.9 V_{f}}=\frac{\tanh ^{-1}(0.9)}{\sqrt{\frac{g H}{2 L^{2}}\left(\Sigma K+\mathrm{f} \frac{L}{D}\right)}}$$

Pressure wave velocity

$$a=\sqrt{\frac{K / \rho_{0}}{1+\frac{K}{E} \frac{D}{t}}}$$
Max Volume of water pumped in one cycle
$$V_{cycle} = A \frac{v_f^2 }{2g }\frac{H_{drive}}{H_{pump}}$$
