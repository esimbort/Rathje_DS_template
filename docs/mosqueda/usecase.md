# Seismic Response of Base Isolated Buildings Considering Pounding to Moat Walls

**Gilberto Mosqueda, University of California, San Diego**  

Summary about Jupiter Notebook goal. Introduction about test. System identification part. Obtained results.

Introductory Text.  High-level overview of product. A condimentum vitae sapien pellentesque habitant morbi tristique.

## HYBRID SHAKE TABLE FORMULATION 

### Citation and Licensing

* Please cite [AUTHORS et al. (20xx) - example of published project](https://doi.org/10.17603/ds2-3zdj-493) to acknowledge the use of any resources from this use case.

* Please cite [Rathje et al. (2017)](https://doi.org/10.1061/(ASCE)NH.1527-6996.0000246) to acknowledge the use of DesignSafe resources.  

* This software is distributed under the GNU General Public License (https://www.gnu.org/licenses/gpl-3.0.html).  

### Description 

Enim ut sem viverra aliquet.  Nisi scelerisque eu ultrices vitae auctor. Scelerisque viverra mauris in aliquam.  Ut morbi tincidunt augue interdum velit euismod in pellentesque massa. Sagittis purus sit amet volutpat consequat mauris nunc congue nisi. Sed adipiscing diam donec adipiscing tristique.  In pellentesque massa placerat duis. Tortor condimentum lacinia quis vel eros donec ac. Sed velit dignissim sodales ut eu sem. Adipiscing elit duis tristique sollicitudin nibh sit amet commodo. Quis risus sed vulputate odio ut.

[Link Example - this goes to Google](https://www.google.com)

## Header 2

Euismod nisi porta lorem mollis aliquam ut. Tincidunt ornare massa eget egestas purus viverra accumsan in. Varius quam quisque id diam vel. Fermentum odio eu feugiat pretium nibh ipsum consequat nisl. Placerat duis ultricies lacus sed turpis tincidunt id aliquet risus. Condimentum vitae sapien pellentesque habitant morbi tristique senectus et netus. Egestas sed sed risus pretium quam vulputate. Posuere morbi leo urna molestie at elementum. Eget magna fermentum iaculis eu non diam. Nisl tincidunt eget nullam non nisi. Sit amet risus nullam eget felis eget nunc lobortis mattis.

### Header2 Subheading

In aliquam sem fringilla ut morbi. Interdum varius sit amet mattis vulputate enim nulla aliquet. Sit amet mattis vulputate enim nulla.  In egestas erat imperdiet sed euismod nisi porta lorem. Eget nulla facilisi etiam dignissim diam.  Facilisi cras fermentum odio eu feugiat. Velit aliquet sagittis id consectetur. Vel quam elementum pulvinar etiam.  Ut diam quam nulla porttitor massa id neque aliquam. Sodales ut etiam sit amet nisl.  Scelerisque varius morbi enim nunc faucibus a. Sit amet volutpat consequat mauris nunc. Et leo duis ut diam.

*Add images to the folder img and use relative path to specify the location of the image.*   

![caption](img/mkdocs-template.png)
> Use case template design


## Header3

Morbi tristique senectus et netus et. Tristique senectus et netus et malesuada fames.  Eu mi bibendum neque egestas congue quisque. Id consectetur purus ut faucibus pulvinar elementum integer enim. Nunc consequat interdum varius sit amet mattis vulputate enim nulla.  Porta nibh venenatis cras sed felis eget. Dui id ornare arcu odio ut sem nulla pharetra diam. Pellentesque habitant morbi tristique senectus et netus et. Commodo nulla facilisi nullam vehicula ipsum a arcu. Nisi porta lorem mollis aliquam ut porttitor leo.

Numbered list 

1. [numbered linked item](https://maps.google.com)
2. second item
3. third item

### Header3 subheading

Ac feugiat sed lectus vestibulum mattis ullamcorper. Et egestas quis ipsum suspendisse ultrices gravida dictum fusce ut. Scelerisque eu ultrices vitae auctor eu augue ut lectus arcu.  Imperdiet proin fermentum leo vel orci porta non pulvinar. Dictumst quisque sagittis purus sit amet. Aliquam purus sit amet luctus. Aliquet bibendum enim facilisis gravida neque convallis a cras. Orci porta non pulvinar neque laoreet suspendisse. Urna neque viverra justo nec ultrices dui.

**Example Table**

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Stampede2| CPU      | 2017     |     
| Frontera | CPU & GPU| 2019     |     

Or use markdown table generator: [https://www.tablesgenerator.com/markdown_tables](https://www.tablesgenerator.com/markdown_tables)


### Math

To generate math equations in markdown.

For inline mode formulas: $`a^2+b^2=c^2`$.

For display mode formulas which appear on a separate line
```math
f(x) = \int_{-\infty}^\infty
\hat f(\xi)\,e^{2 \pi i \xi x}
\,d\xi
```

### Code

``` python
import tensorflow as tf
```

Highlight specific lines of the code

``` python hl_lines="3 4"
""" Bubble sort """
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

``` python
from IPython.utils import io

def myfunc():
    # Install a pip package in the current Jupyter kernel
    import sys
    !{sys.executable} -m pip install --user ipyfilechooser
with io.capture_output() as captured:
    myfunc()
    
from ipyfilechooser import FileChooser

# Create and display a FileChooser widget
fc = FileChooser('/home/jupyter/NEES/NEES-2008-0571.groups/Experiment-8')
#display(fc)
```
Description of cell 1

Description of what is excecuted in this cell 1.
Why do we need to install a pip package in the current Jupyter kernel? What does FileChooser execute?

``` python
import numpy as np
import pandas as pd
import linecache
pd.set_option('display.max_rows', None)

#path=fc.selected
path='/home/jupyter/NEES/NEES-2008-0571.groups/Experiment-8/Trial-12/Rep-1/Unprocessed_Data/fbgm152s3.asc'
data_open = open(path) # open data and store data
print(data_open)
data = np.loadtxt(path,skiprows=6,unpack=True) # convert to readable data
n,c = data.shape
print('n=',n)
print('c=',c)
n_channels=len(data)
print(n_channels)
info_head=[]
for i in range(0,n_channels):
    info_head.append("CHAN_"+str(i+1))#create the names of the channels

data1 = pd.read_table(path,delimiter='\s+',nrows=6,skiprows=4,names=info_head)
print(data1)
DESC_CHAN=[]
UNITS_CHAN =[]

for k in range(0,n_channels):
    DESC_CHAN.append((data1.loc[0, info_head[k]]))
    UNITS_CHAN.append((data1.loc[1, info_head[k]]))  
    
tab=pd.DataFrame(list(zip(DESC_CHAN,UNITS_CHAN)), columns = ['Description','Units'])
display(tab)
```
Description of cell 2

Description of what is excecuted in this cell 2
Main steps of uploading, reading data, and getting ready to process it.

``` python
import matplotlib.pyplot as plt
from matplotlib import animation

time=data[0]
print(time.shape)
A1=data[25]
A2=data[26]
cc = np.array([ A1, A2 ])
print(cc.shape)
av=np.mean( np.array([ A1, A2 ]), axis=0 )
print(A1.shape)
print(A2.shape)
print(av.shape)

story_1=np.mean( np.array([ data[30], data[31] ]), axis=0 )
story_2=np.mean( np.array([ data[32], data[33] ]), axis=0 )
story_3=np.mean( np.array([ data[34], data[35] ]), axis=0 )

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(time,A1, label='A1')
ax.plot(time,A2, label='A2')
ax.plot(time,av, label='Average')
ax.set_xlabel('Time [seconds]')
ax.set_ylabel('Acceleration [g]')
ax.set_title('Base Plate')
ax.legend()

plt.show()

fig, ax1=plt.subplots(1, figsize=(9.5,5))
ax1.plot(time,data[30], label='A6')
ax1.plot(time,data[31], label='A7')
ax1.plot(time,story_1, label='Average')
ax1.set_xlabel('Time [seconds]')
ax1.set_ylabel('Acceleration [g]')
ax1.set_title('Level 1')
ax1.legend()

plt.show()

fig, ax2=plt.subplots(1, figsize=(9.5,5))
ax2.plot(time,data[32], label='A8')
ax2.plot(time,data[33], label='A9')
ax2.plot(time,story_2, label='Average')
ax2.set_xlabel('Time [seconds]')
ax2.set_ylabel('Acceleration [g]')
ax2.set_title('Level 2')
ax2.legend()

plt.show()

fig, ax3=plt.subplots(1, figsize=(9.5,5))
ax3.plot(time,data[34], label='A10')
ax3.plot(time,data[35], label='A11')
ax3.plot(time,story_3, label='Average')
ax3.set_xlabel('Time [seconds]')
ax3.set_ylabel('Acceleration [g]')
ax3.set_title('Level 3')
ax3.legend()

plt.show()
```

Description of cell 3

Description of what is excecuted in this cell 3
Brief analysis of shown figures.

``` python
# Transfer Function:

from scipy import signal
import math

fs = len(time)/time[len(time)-1] # sampling frequency
print(fs)
nfft = len(time) # length of the FFT used

fxx, Sxx = signal.csd(av, av, fs, 'hann', None, None, nfft)

# 3rd Floor

fyy3, Syy3 = signal.csd(story_3, story_3, fs, 'hann', None, None, nfft)
fxy3, Sxy3 = signal.csd(av, story_3, fs, 'hann', None, None, nfft)

H1_abs3 = abs(Sxy3/Sxx)
H2_abs3 = abs(Syy3/Sxy3)

Hv_abs_nfcn3 = H1_abs3*H2_abs3

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(fxy3, Hv_abs_nfcn3)
plt.show()

# 2nd Floor

fyy2, Syy2 = signal.csd(story_2, story_2, fs, 'hann', None, None, nfft)
fxy2, Sxy2 = signal.csd(av, story_2, fs, 'hann', None, None, nfft)

H1_abs2 = abs(Sxy2/Sxx)
H2_abs2 = abs(Syy2/Sxy2)

Hv_abs_nfcn2 = H1_abs2*H2_abs2

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(fxy2, Hv_abs_nfcn2)
plt.show()

# 1st Floor

fyy1, Syy1 = signal.csd(story_1, story_1, fs, 'hann', None, None, nfft)
fxy1, Sxy1 = signal.csd(av, story_1, fs, 'hann', None, None, nfft)

H1_abs1 = abs(Sxy1/Sxx)
H2_abs1 = abs(Syy1/Sxy1)

Hv_abs_nfcn1 = H1_abs1*H2_abs1

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(fxy1, Hv_abs_nfcn1)
plt.show()

```
Description of cell 4

Description of what is excecuted in this cell 4
Description of system Identification process. What does signal.csd implement? Regression analyisis - Supervised ML

``` phyton
# CSD Outputs

font = {'family' : 'normal',
        'weight' : 'normal',
        'size'   : 22}

plt.rc('font', **font)

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(fxy3[0:2000:1], Hv_abs_nfcn3[0:2000:1])
ax.set_xlabel('Frequency (Hz)')
ax.set_ylabel('Acceleration (g^2/Hz)')
ax.set_title('Third Story CSD')
plt.show()

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(fxy3[0:2000:1], Hv_abs_nfcn2[0:2000:1])
ax.set_xlabel('Frequency (Hz)')
ax.set_ylabel('Acceleration (g^2/Hz)')
ax.set_title('Second Story CSD')
plt.show()

fig, ax=plt.subplots(1, figsize=(9.5,5))
ax.plot(fxy3[0:2000:1], Hv_abs_nfcn1[0:2000:1])
ax.set_xlabel('Frequency (Hz)')
ax.set_ylabel('Acceleration (g^2/Hz)')
ax.set_title('First Story CSD')
plt.show()
```
Description of cell 5

Description of what is excecuted in this cell 5
Analysis of obtained results.

``` python
from scipy.signal import argrelextrema
from scipy import interpolate

# update if structure has more than 3 stories

max3index = argrelextrema(Hv_abs_nfcn3[0:2000:1], np.greater)
max2index = argrelextrema(Hv_abs_nfcn2[0:2000:1], np.greater)
max1index = argrelextrema(Hv_abs_nfcn1[0:2000:1], np.greater)

floor1disp = [0,0,0]
floor2disp = [0,0,0]
floor3disp = [0,0,0]

for i in [0,1,2]:
    if Sxy1[max1index[0][i]]/Sxx[max1index[0][i]] < 0 or Syy1[max1index[0][i]]/Sxy1[max1index[0][i]] < 0:
        floor1disp[i] = -Hv_abs_nfcn1[max1index[0][i]]/fxy1[max1index[0][i]]**4
    else:
        floor1disp[i] = Hv_abs_nfcn1[max1index[0][i]]/fxy1[max1index[0][i]]**4
        
    if Sxy2[max2index[0][i]]/Sxx[max2index[0][i]] < 0 or Syy2[max2index[0][i]]/Sxy2[max2index[0][i]] < 0:
        floor2disp[i] = -Hv_abs_nfcn2[max2index[0][i]]/fxy2[max2index[0][i]]**4
    else:
        floor2disp[i] = Hv_abs_nfcn2[max2index[0][i]]//fxy2[max2index[0][i]]**4
        
    if Sxy3[max3index[0][i]]/Sxx[max3index[0][i]] < 0 or Syy3[max3index[0][i]]/Sxy3[max3index[0][i]] < 0:
        floor3disp[i] = -Hv_abs_nfcn3[max3index[0][i]]/fxy3[max3index[0][i]]**4
    else:
        floor3disp[i] = Hv_abs_nfcn3[max3index[0][i]]/fxy3[max3index[0][i]]**4

mode1 = [0,floor1disp[0],floor2disp[0],floor3disp[0]]/max([abs(floor1disp[0]),abs(floor2disp[0]),abs(floor3disp[0])])
mode2 = [0,floor1disp[1],floor2disp[1],floor3disp[1]]/max([abs(floor1disp[1]),abs(floor2disp[1]),abs(floor3disp[1])])
mode3 = [0,floor1disp[2],floor2disp[2],floor3disp[2]]/max([abs(floor1disp[2]),abs(floor2disp[2]),abs(floor3disp[2])])
story = [0,1,2,3]

story_spline = np.linspace(0, 3, 300)
m1_Spline = interpolate.make_interp_spline(story, mode1)
mode1_spline = m1_Spline(story_spline)
m2_Spline = interpolate.make_interp_spline(story, mode2)
mode2_spline = m2_Spline(story_spline)
m3_Spline = interpolate.make_interp_spline(story, mode3)
mode3_spline = m3_Spline(story_spline)

fig, ax=plt.subplots(1, figsize=(3,5))
ax.plot(mode1, story)
ax.set_xlabel('Modal Displacement')
ax.set_ylabel('Story')
ax.set_title('Mode 1 Shape')
plt.show()

fig, ax=plt.subplots(1, figsize=(3,5))
ax.plot(mode2, story)
ax.set_xlabel('Modal Displacement')
ax.set_ylabel('Story')
ax.set_title('Mode 2 Shape')
plt.show()

fig, ax=plt.subplots(1, figsize=(3,5))
ax.plot(mode3, story)
ax.set_xlabel('Modal Displacement')
ax.set_ylabel('Story')
ax.set_title('Mode 3 Shape')
plt.show()

fig, ax=plt.subplots(1, figsize=(8,10))
ax.plot(mode1, story, mode2, story, mode3, story)
ax.set_xlabel('Modal Displacement')
ax.set_ylabel('Story')
ax.set_title('Modal Shapes')
ax.legend(['Mode 1', 'Mode 2', 'Mode 3'])
plt.show()
```
Description of cell 6

Description of what is excecuted in this cell 6
Description of general procedure for n dofs. So far, the program is written to compute vibration modes for 3 dofs. This function needs to be generalized.
