# Statistik
Evaluasi Model
# <font color='coral'><center>Evaluasi Model untuk Regresi</center></font>
Using: Python

Contoh pengukuran model untuk <font color = 'red'> regresi </font>:
1. Mean Absolute Error (MAE)
2. Relative Absolute Error (RAE)
3. Mean Squared Error (MSE)
4. Relative Squared Error (RSE)
5. Root Mean Squared Error (RMSE)
6. Mean Absolute Percentage Error (MAPE)
7. Mean Percentage Error (MPE)
8. R-squared

Import `library numpy` yang nantinya digunakan untuk membuat data type array
```python
import numpy as np
```
jika error, install terlebih dahulu
```python
!pip install numpy
```
### <font color='coral'>Misal data aktual dan data prediksinya sudah diketahui:</font>
```python
y_act = np.array([1, 2 ,1,1,1,1,2,2,1])
y_pre = np.array([1,1.5,1,1,1,1,2,2,1])
```
<font color='coral'>1. Mean Absolute Error (MAE):</font>
![image](https://user-images.githubusercontent.com/47238141/147392962-41768713-0d04-4196-9629-73d927c72005.png)
```python
n = len(y_act)
MAE = (1/n)*sum(abs(y_act-y_pre))
print('MAE (cara 1):',MAE)

## Cara 2 (Using Numpy):
print('MAE (cara 2):',np.mean(np.abs(y_act - y_pre)))

## Cara 3 (Using Sklearn):
from sklearn.metrics import mean_absolute_error
print('MAE (cara 3):', mean_absolute_error(y_act,y_pre))
```
Output:
```
MAE (cara 1): 0.05555555555555555
MAE (cara 2): 0.05555555555555555
MAE (cara 3): 0.05555555555555555
```
<font color='coral'>2. Relative Absolute Error (RAE) :</font>
![image](https://user-images.githubusercontent.com/47238141/147392999-4fe99ab2-6a07-4961-8cb1-4a3915556642.png)
```python
RSE = (np.sum(abs(y_act - y_pre)))/(np.sum(abs(y_act - np.mean(y_act))))
print('RSE : ', RSE)
```
Output:
```
RSE :  0.125
```
<font color='coral'>3. Mean Square Error (MSE):</font>
![image](https://user-images.githubusercontent.com/47238141/147393029-6e08f753-25cd-46be-b82e-e38f12a1a739.png)
```python
MSE = np.mean(np.square(y_act - y_pre))
print('MSE :',MSE)
```
Output:
```
MSE : 0.027777777777777776
```
<font color='coral'>4. Relative Squared Error (RSE):</font>
![image](https://user-images.githubusercontent.com/47238141/147393040-6c605c2c-a326-4494-b74d-851cf27c5a24.png)
```python
RSE = np.sum(np.square(y_act - y_pre)) / np.sum(np.square(y_act - np.mean(y_act)))
print('RSE :',RSE)
```
Output:
```
RSE : 0.125
```
<font color='coral'>5. Root Mean Square Error (RMSE):</font>
![image](https://user-images.githubusercontent.com/47238141/147393067-7bd73dfe-cd31-4ebf-9c27-0e77864fa14f.png)

```python
RMSE = np.sqrt(np.mean(np.square(y_act - y_pre)))
print('RMSE : ', RMSE)
```
Output:
```
RMSE :  0.16666666666666666
```
<font color='coral'>6. Mean Absolute Percentage Error (MAPE):</font>
![image](https://user-images.githubusercontent.com/47238141/147393088-cc0bcc6f-7fc2-4d9d-a6a2-dc6a8d4080f8.png)
```python
MAPE = np.mean(np.abs(y_act - y_pre)) * 100
print('MAPE : ', round(MAPE,2), '%', sep='')
```
Output:
```
MAPE : 5.56%
```
<font color='coral'>7. Mean Percentage Error (MPE):</font>
![image](https://user-images.githubusercontent.com/47238141/147393114-1f9fb0fb-8f4d-48ec-b357-637fdafca9eb.png)
```python
MPE = np.mean(y_act - y_pre) * 100
print('MAPE : ', round(MPE,2), '%', sep='')
```
Output:
```
MAPE : 5.56%
```
<font color='coral'>8. R-Square:</font>
![image](https://user-images.githubusercontent.com/47238141/147393121-3a086b97-bad0-47fa-b0ae-2a1f9bdcd2bf.png)
```python
## Cara 1:
RSE = np.sum(np.square(y_act - y_pre)) / np.sum(np.square(y_act - np.mean(y_act)))
r2 = 1-RSE
print('R2 (cara 1):',r2)

## Cara 2:
from sklearn.metrics import r2_score
print('R2 (cara 2):',r2_score(y_act, y_pre))
```
Output:
```
R2 (cara 1): 0.875
R2 (cara 2): 0.875
```
![image](https://user-images.githubusercontent.com/47238141/147393138-5ebf5969-ac7e-40ae-aed1-fed6e735a63c.png)










