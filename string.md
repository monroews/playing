```python
from aguaclara.core.units import unit_registry as u
import aguaclara.research.environmental_processes_analysis as epa
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import aguaclara.core.utility as ut

# this is the velocity for a low rate trickling filter.
# I haven't found the rate for high rate trickling filters
v_trickling = (0.06 * u.gal/u.min/u.ft**2).to(u.mm/u.s)
v_trickling
String_spacing= 6* u.mm
String_flow = v_trickling*String_spacing**2
print('The flowrate per string to match the velocity of low rate trickling filters is',ut.round_sf(String_flow.to(u.mL/u.min),2))
String_H = 4 * u.m
# mass of wetted string measured by Marcin
string_water_volume = 0.3 * u.mL/u.m


String_capillary_flow_max = 0.3 * u.mL/u.min


theta = (string_water_volume/String_capillary_flow_max*String_H).to(u.min)
theta
bunch = 16
string = 5*u.mL/u.min/bunch
string
minpump = 0.5 * u.mL/u.min


```
