# Create dataFrame

Clone the repo and run the following commands to start a venv and install the libraries needed


```python
#start a virtual enviroment
python3 -m venv .venv
source .venv/bin/activate


```

# Code explenation

This first snippet will create a dataframe from the csv object and will print the first 10 rows of the dataframes
beacuse of the google column that appears in the data set we neet to ignore the rows that makes the df object read everything as strings


```python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('google_5yr_one.csv', na_values=['GOOGL', 'null', 'N/A'])

df.head(11)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Close</th>
      <th>High</th>
      <th>Low</th>
      <th>Open</th>
      <th>Volume</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2020-06-04</td>
      <td>70.378517</td>
      <td>71.723094</td>
      <td>69.965992</td>
      <td>71.497169</td>
      <td>26982000.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2020-06-05</td>
      <td>71.658401</td>
      <td>71.970910</td>
      <td>70.046107</td>
      <td>70.445200</td>
      <td>42642000.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2020-06-08</td>
      <td>72.057487</td>
      <td>72.105256</td>
      <td>70.885091</td>
      <td>70.974667</td>
      <td>33878000.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2020-06-09</td>
      <td>72.258530</td>
      <td>73.040793</td>
      <td>71.774842</td>
      <td>71.918162</td>
      <td>33624000.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2020-06-10</td>
      <td>72.886528</td>
      <td>73.288104</td>
      <td>72.371990</td>
      <td>72.727787</td>
      <td>31762000.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2020-06-11</td>
      <td>69.761475</td>
      <td>72.234651</td>
      <td>69.587805</td>
      <td>71.708662</td>
      <td>47144000.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2020-06-12</td>
      <td>70.309853</td>
      <td>71.384214</td>
      <td>68.960302</td>
      <td>70.953770</td>
      <td>36676000.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2020-06-15</td>
      <td>70.698990</td>
      <td>70.910974</td>
      <td>69.029968</td>
      <td>69.143925</td>
      <td>30468000.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2020-06-16</td>
      <td>71.979370</td>
      <td>72.511821</td>
      <td>71.109528</td>
      <td>72.105264</td>
      <td>30648000.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2020-06-17</td>
      <td>72.281425</td>
      <td>72.762129</td>
      <td>71.415069</td>
      <td>72.301335</td>
      <td>30610000.0</td>
    </tr>
  </tbody>
</table>
</div>



# simple type snippet



```python
df.dtypes
```




    Date       object
    Close     float64
    High      float64
    Low       float64
    Open      float64
    Volume    float64
    dtype: object



# print general statistics


```python
print(df.describe())
```

                 Close         High          Low         Open        Volume
    count  1255.000000  1255.000000  1255.000000  1255.000000  1.255000e+03
    mean    127.343522   128.767640   125.894397   127.286213  3.211913e+07
    std      31.589957    31.873115    31.332366    31.626389  1.354981e+07
    min      67.802834    69.567407    67.260929    67.693363  9.312000e+06
    25%     102.415359   103.588002   101.102139   102.211330  2.333280e+07
    50%     128.465805   130.137811   126.953037   128.635000  2.882800e+07
    75%     147.319427   148.956410   146.023874   147.533393  3.675800e+07
    max     206.142593   206.811821   202.576693   203.156027  1.274901e+08


# Get data from a specifik conditon


```python
open_over_200 = df[df["Open"] > 200]
open_over_200
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Close</th>
      <th>High</th>
      <th>Low</th>
      <th>Open</th>
      <th>Volume</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1172</th>
      <td>2025-01-31</td>
      <td>203.785309</td>
      <td>205.243621</td>
      <td>201.567861</td>
      <td>201.767628</td>
      <td>32042000.0</td>
    </tr>
    <tr>
      <th>1173</th>
      <td>2025-02-03</td>
      <td>200.998505</td>
      <td>203.515610</td>
      <td>199.869815</td>
      <td>200.459133</td>
      <td>27838300.0</td>
    </tr>
    <tr>
      <th>1174</th>
      <td>2025-02-04</td>
      <td>206.142593</td>
      <td>206.811821</td>
      <td>202.576693</td>
      <td>203.156027</td>
      <td>43856400.0</td>
    </tr>
  </tbody>
</table>
</div>


