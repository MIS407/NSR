# -*- coding: utf-8 -*-
"""
Created on Tue Dec  2 17:13:20 2014

@author: Braden
"""

import csv
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from urllib import request
from datetime import datetime


filename = "results2.csv"

#Reads csv file into dataframe
df = pd.read_csv(filename, encoding='latin1')

#Strips off information we don't need about the date
df['SaleDate'] = df['SaleDate'].map(lambda x: str(x)[6:])

#Converts date to Floating point number
df['SaleDate'] = df['SaleDate'].astype(int)





#Drops any rows that do not contain any information in them
df2 = df.dropna(how='any')

#Sale date
format = "%Y"
times = pd.to_datetime(df2.SaleDate, format=format)
df2.set_index(times, inplace=True)




#Display Averages of the Data for insight
print ('The averages of the data: \n', np.round(df.mean(), decimals=2))

#Year and price before outliers are taken out


#plots



dfYear = df2[df2.Yr == 1920]

#Average of 1920 house prices
dfYear.plot(kind='bar', x='Yr', y='Price')

#Year and Price without outliers taken out
df2.plot(kind='scatter', x='Yr', y='Price')



#Year and Price after outliers taken out
df3 = df2[df2.Price < 350000]
df3.plot(kind='scatter', x='Yr', y='Price')


#Groups Sale Dates together and averages their prices and plots in bar graph
#df2.groupby('SaleDate').Price.mean().plot(kind='bar')






'''
#plots
df.plot(kind='scatter', x='Yr', y='Price');
df.plot(kind='line', x='Yr', y='Price');
df.plot(kind='scatter', x='Bath (1/2 + full)', y='Price');
df.plot(kind='scatter', x='TBr', y='Price');
'''

'''
#Other plots
df.plot()
df.Price.plot()
'''


