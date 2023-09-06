```python
import pandas as pd 
import numpy as np
```


```python
df = pd.read_csv(r'C:\Users\sparsh sharma\Downloads\hotel data.txt',delimiter='\t')
df.head()

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
      <th>Company</th>
      <th>Person Name</th>
      <th>Room number</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1-Jan-2022</td>
      <td>Avamba</td>
      <td>Anatole Ridehalgh</td>
      <td>4008.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1-Jan-2022</td>
      <td>Fatz</td>
      <td>Aldrich McKevin</td>
      <td>2002.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1-Jan-2022</td>
      <td>Leexo</td>
      <td>Stanley Hadrill</td>
      <td>4012.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1-Jan-2022</td>
      <td>Rhyzio</td>
      <td>Lyndell Tice</td>
      <td>1006.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe()
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
      <th>Room number</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>153.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>3079.326797</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1718.791186</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1001.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2001.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3008.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>4010.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>7002.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['Company'].value_counts()
```




    Company
    Leexo           3
    Fivechat        3
    Quinu           3
    Jabbersphere    2
    Twitterlist     2
                   ..
    Topiclounge     1
    Shufflebeat     1
    Skyvu           1
    Youspan         1
    Twitterworks    1
    Name: count, Length: 114, dtype: int64




```python
df.dropna()
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
      <th>Company</th>
      <th>Person Name</th>
      <th>Room number</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1-Jan-2022</td>
      <td>Avamba</td>
      <td>Anatole Ridehalgh</td>
      <td>4008.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1-Jan-2022</td>
      <td>Fatz</td>
      <td>Aldrich McKevin</td>
      <td>2002.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1-Jan-2022</td>
      <td>Leexo</td>
      <td>Stanley Hadrill</td>
      <td>4012.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1-Jan-2022</td>
      <td>Rhyzio</td>
      <td>Lyndell Tice</td>
      <td>1006.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1-Jan-2022</td>
      <td>Eadel</td>
      <td>Broderic Handscombe</td>
      <td>3015.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>186</th>
      <td>1-Jan-2022</td>
      <td>Tagpad</td>
      <td>Stephani Lafee</td>
      <td>1015.0</td>
    </tr>
    <tr>
      <th>187</th>
      <td>1-Jan-2022</td>
      <td>Meevee</td>
      <td>Victoria Lavery</td>
      <td>7002.0</td>
    </tr>
    <tr>
      <th>191</th>
      <td>1-Jan-2022</td>
      <td>Fivechat</td>
      <td>Corabella Saye</td>
      <td>4008.0</td>
    </tr>
    <tr>
      <th>192</th>
      <td>1-Jan-2022</td>
      <td>Innojam</td>
      <td>Leandra Potapczuk</td>
      <td>5002.0</td>
    </tr>
    <tr>
      <th>193</th>
      <td>1-Jan-2022</td>
      <td>Twitterworks</td>
      <td>Valentia Ledson</td>
      <td>1010.0</td>
    </tr>
  </tbody>
</table>
<p>134 rows × 4 columns</p>
</div>




```python
mask = df['Room number'].isna()

df['Text value'] = np.where(mask,df['Date'], np.nan)
df
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
      <th>Company</th>
      <th>Person Name</th>
      <th>Room number</th>
      <th>Text value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1-Jan-2022</td>
      <td>Avamba</td>
      <td>Anatole Ridehalgh</td>
      <td>4008.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1-Jan-2022</td>
      <td>Fatz</td>
      <td>Aldrich McKevin</td>
      <td>2002.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1-Jan-2022</td>
      <td>Leexo</td>
      <td>Stanley Hadrill</td>
      <td>4012.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1-Jan-2022</td>
      <td>Rhyzio</td>
      <td>Lyndell Tice</td>
      <td>1006.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>190</th>
      <td>Cleartrip</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cleartrip</td>
    </tr>
    <tr>
      <th>191</th>
      <td>1-Jan-2022</td>
      <td>Fivechat</td>
      <td>Corabella Saye</td>
      <td>4008.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>192</th>
      <td>1-Jan-2022</td>
      <td>Innojam</td>
      <td>Leandra Potapczuk</td>
      <td>5002.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>193</th>
      <td>1-Jan-2022</td>
      <td>Twitterworks</td>
      <td>Valentia Ledson</td>
      <td>1010.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>194</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Hotels</td>
    </tr>
  </tbody>
</table>
<p>195 rows × 5 columns</p>
</div>




```python
df['Text value'].fillna(method='bfill', inplace=True)
df
```

    C:\Users\sparsh sharma\AppData\Local\Temp\ipykernel_20464\1832655442.py:1: FutureWarning: Series.fillna with 'method' is deprecated and will raise in a future version. Use obj.ffill() or obj.bfill() instead.
      df['Text value'].fillna(method='bfill', inplace=True)
    




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
      <th>Company</th>
      <th>Person Name</th>
      <th>Room number</th>
      <th>Text value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1-Jan-2022</td>
      <td>Avamba</td>
      <td>Anatole Ridehalgh</td>
      <td>4008.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1-Jan-2022</td>
      <td>Fatz</td>
      <td>Aldrich McKevin</td>
      <td>2002.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1-Jan-2022</td>
      <td>Leexo</td>
      <td>Stanley Hadrill</td>
      <td>4012.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1-Jan-2022</td>
      <td>Rhyzio</td>
      <td>Lyndell Tice</td>
      <td>1006.0</td>
      <td>Booking</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>190</th>
      <td>Cleartrip</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cleartrip</td>
    </tr>
    <tr>
      <th>191</th>
      <td>1-Jan-2022</td>
      <td>Fivechat</td>
      <td>Corabella Saye</td>
      <td>4008.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>192</th>
      <td>1-Jan-2022</td>
      <td>Innojam</td>
      <td>Leandra Potapczuk</td>
      <td>5002.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>193</th>
      <td>1-Jan-2022</td>
      <td>Twitterworks</td>
      <td>Valentia Ledson</td>
      <td>1010.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>194</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Hotels</td>
    </tr>
  </tbody>
</table>
<p>195 rows × 5 columns</p>
</div>




```python
df
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
      <th>Company</th>
      <th>Person Name</th>
      <th>Room number</th>
      <th>Text value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1-Jan-2022</td>
      <td>Avamba</td>
      <td>Anatole Ridehalgh</td>
      <td>4008.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1-Jan-2022</td>
      <td>Fatz</td>
      <td>Aldrich McKevin</td>
      <td>2002.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1-Jan-2022</td>
      <td>Leexo</td>
      <td>Stanley Hadrill</td>
      <td>4012.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1-Jan-2022</td>
      <td>Rhyzio</td>
      <td>Lyndell Tice</td>
      <td>1006.0</td>
      <td>Booking</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>190</th>
      <td>Cleartrip</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cleartrip</td>
    </tr>
    <tr>
      <th>191</th>
      <td>1-Jan-2022</td>
      <td>Fivechat</td>
      <td>Corabella Saye</td>
      <td>4008.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>192</th>
      <td>1-Jan-2022</td>
      <td>Innojam</td>
      <td>Leandra Potapczuk</td>
      <td>5002.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>193</th>
      <td>1-Jan-2022</td>
      <td>Twitterworks</td>
      <td>Valentia Ledson</td>
      <td>1010.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>194</th>
      <td>Hotels</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Hotels</td>
    </tr>
  </tbody>
</table>
<p>195 rows × 5 columns</p>
</div>




```python
df.dropna(inplace=True)
df
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
      <th>Company</th>
      <th>Person Name</th>
      <th>Room number</th>
      <th>Text value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1-Jan-2022</td>
      <td>Avamba</td>
      <td>Anatole Ridehalgh</td>
      <td>4008.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1-Jan-2022</td>
      <td>Fatz</td>
      <td>Aldrich McKevin</td>
      <td>2002.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1-Jan-2022</td>
      <td>Leexo</td>
      <td>Stanley Hadrill</td>
      <td>4012.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1-Jan-2022</td>
      <td>Rhyzio</td>
      <td>Lyndell Tice</td>
      <td>1006.0</td>
      <td>Booking</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1-Jan-2022</td>
      <td>Eadel</td>
      <td>Broderic Handscombe</td>
      <td>3015.0</td>
      <td>Booking</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>186</th>
      <td>1-Jan-2022</td>
      <td>Tagpad</td>
      <td>Stephani Lafee</td>
      <td>1015.0</td>
      <td>Expedia</td>
    </tr>
    <tr>
      <th>187</th>
      <td>1-Jan-2022</td>
      <td>Meevee</td>
      <td>Victoria Lavery</td>
      <td>7002.0</td>
      <td>Expedia</td>
    </tr>
    <tr>
      <th>191</th>
      <td>1-Jan-2022</td>
      <td>Fivechat</td>
      <td>Corabella Saye</td>
      <td>4008.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>192</th>
      <td>1-Jan-2022</td>
      <td>Innojam</td>
      <td>Leandra Potapczuk</td>
      <td>5002.0</td>
      <td>Hotels</td>
    </tr>
    <tr>
      <th>193</th>
      <td>1-Jan-2022</td>
      <td>Twitterworks</td>
      <td>Valentia Ledson</td>
      <td>1010.0</td>
      <td>Hotels</td>
    </tr>
  </tbody>
</table>
<p>134 rows × 5 columns</p>
</div>




```python

```
