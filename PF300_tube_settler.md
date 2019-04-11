```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
Sed_D = 36*u.inch
Tube_D = 3/8 * u.inch
Tube_D.to(u.mm)
Tube_angle = 60 * u.degree
Sed_long_D = Sed_D/np.sin(Plate_angle)
Sed_long_D
Plate_H = 12 * u.inch
Tube_S_horizontal = Tube_D/np.sin(Plate_angle)
Tube_S_horizontal
48*u.inch/Tube_S_horizontal
(4*u.ft/(8*u.inch)).to(u.dimensionless)

Tube_S_horizontal/6

Tube_H = 12*u.inch
Up_V = 1 * u.mm/u.s

def Tube_Vc(Tube_H=Tube_H,Tube_D=Tube_D,Up_V=Up_V,Tube_angle=Tube_angle):
  Tube_Vc = Up_V/(Tube_H/Tube_D*np.cos(Tube_angle)+1)
  return Tube_Vc.to(u.mm/u.s)

Tube_Vc(6*u.inch)

```
WE can achieve a much lower capture velocity in a self supporting pack. 6 inch height would be sufficient to achieve our 0.12 mm/s. 

$${V_c} = \frac{{{V_{Plate \uparrow }}}}{{\frac{L}{D}\sin \alpha \cos \alpha  + 1}}$$

$${V_c} = \frac{{{V_{Tube \uparrow }}}}{{\frac{h}{D} \cos \alpha  + 1}}$$


Also see the picture of nominal 3/8” cell PC Honeycomb in black. There is also a 10mm cell PP in natural above it. You can see the circular cell geometry creates a small interstitial area of open area between the cells.  Cell walls are about 5 mil for PC (5 pcf density) and 10 mil for PP (4 pcf density). The 3/8” cell is currently our largest PC cell Honeycomb.  Potential option is a ½”. The PP Honeycomb can go up to a 12mm cell.

 ![graph](https://github.com/monroews/playing/raw/master/images/plasticore.jpg)

Below is a sketch of 12" high tube settlers with 3/8" diameter tubes.

 ![graph](https://github.com/monroews/playing/raw/master/images/Tube_settlers.png)
