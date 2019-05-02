```Python
from aguaclara.core.units import unit_registry as u
from aguaclara.core import utility as ut
from aguaclara.core import physchem as pc
import aguaclara.design.floc as floc
from aguaclara.research import floc_model as fm
import matplotlib.pyplot as plt
import numpy as np
energy = (404 *u.kW*u.hr/(u.Mgal)).to(u.J/u.L)
energy
Temp=20*u.degC
height = (energy/(u.gravity*pc.density_water(Temp))).to(u.m)
height
print('The energy used to aerate the wastewater is equivalent to elevating the wastewater', height)
```

Energy for aeration from Table 3 in Total Energy Consumption for Municipal Wastewater Treatment, 1978
https://nepis.epa.gov/Exe/ZyNET.exe/9100SR0P.txt?ZyActionD=ZyDocument&Client=EPA&Index=1976%20Thru%201980&Docs=&Query=&Time=&EndTime=&SearchMethod=1&TocRestrict=n&Toc=&TocEntry=&QField=&QFieldYear=&QFieldMonth=&QFieldDay=&UseQField=&IntQFieldOp=0&ExtQFieldOp=0&XmlQuery=&File=D%3A%5CZYFILES%5CINDEX%20DATA%5C76THRU80%5CTXT%5C00000018%5C9100SR0P.txt&User=ANONYMOUS&Password=anonymous&SortMethod=h%7C-&MaximumDocuments=1&FuzzyDegree=0&ImageQuality=r75g8/r75g8/x150y150g16/i425&Display=hpfr&DefSeekPage=x&SearchBack=ZyActionL&Back=ZyActionS&BackDesc=Results%20page&MaximumPages=1&ZyEntry=2#
