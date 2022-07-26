# codes
Python 3.7.4 (default, Aug  9 2019, 18:34:13) [MSC v.1915 64 bit (AMD64)]
Type "copyright", "credits" or "license" for more information.

IPython 7.8.0 -- An enhanced Interactive Python.

import pandas as pd

import numpy as np

import matplotlib as plt

import datetime

from datetime import datetime

ig=pd.read_csv("F:/DATABASES/forpython/igloandisbursed.csv")

ig.rename(columns = {'datetime':'date'}, inplace = True)

ig['date']=pd.to_datetime(ig['date'], format="'%H:%M.%S%f'")

ig['date']=pd.to_datetime(ig['date'], format="'%Y %M %D %H %M %S %f'")
Traceback (most recent call last):

 ig['date']=pd.to_datetime(ig['date'])

ig
ig['date']=pd.to_datetime(ig['date'],format='%Y-%m-%d %H:%M:%S.%f')

igindex = ig.set_index('date')

igindex
Out[14]: 
                     votecode    pnum  ... approved    luwho

[1031 rows x 18 columns]

igfixed=igindex[igindex['tranname'].str.match('FreshTxn')]

igfixed
Out[16]: 
                     votecode    pnum  ... approved     luwho
[579 rows x 18 columns]

igfixedfew=igfixed[['names','newamt','tranname','interest']]

igfixedfew
Out[18]: 
                                          names  newamt  tranname  interest
date                                                                       

[579 rows x 4 columns]

igfixedfew.plot()
￼

_ =igfixedfew['newamt'].plot(figsize=(12,8));

￼

= igfixedfew.plot(figsize=(12,8));
    = igfixedfew.plot(figsize=(12,8));

igfixedfew.plot(figsize=(12,8));

￼

plt.bar(igfixedfew.index, msftV)
Traceback (most recent call last):

  File "<ipython-input-23-f6de311fb6a4>", line 1, in <module>
    plt.bar(igfixedfew.index, msftV)

AttributeError: module 'matplotlib' has no attribute 'bar'
