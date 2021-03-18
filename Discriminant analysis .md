```python
import pandas as pd
```


```python
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
```


```python
dataset=pd.read_excel("2.Discriminant Analysis.xlsx",sheet_name=0)
```


```python
dataset.columns
```




    Index(['ResortVisit', 'AnnualFamilyIncome', 'AttitudeTowardTravel',
           'ImportanceAttachedtoFamilyVacatioin', 'HouseholdSize',
           'AgeofHeadofHousehold', 'AmountSpentonFamilyVacation'],
          dtype='object')




```python
dataset1=dataset.isnull().sum()
dataset1
```




    ResortVisit                            0
    AnnualFamilyIncome                     0
    AttitudeTowardTravel                   0
    ImportanceAttachedtoFamilyVacatioin    0
    HouseholdSize                          0
    AgeofHeadofHousehold                   0
    AmountSpentonFamilyVacation            0
    dtype: int64




```python
Y=dataset.ResortVisit #dep var
```


```python
X=dataset[['AnnualFamilyIncome', 'AttitudeTowardTravel',
       'ImportanceAttachedtoFamilyVacatioin', 'HouseholdSize',
       'AgeofHeadofHousehold', 'AmountSpentonFamilyVacation']]
```


```python
clf=LinearDiscriminantAnalysis()

```


```python
clf.fit(X,Y)
```




    LinearDiscriminantAnalysis()




```python
print(clf.predict(X))
```

    [1 1 1 2 1 1 2 1 1 1 1 1 1 1 1 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2]
    


```python
clf.score(X,Y)
```




    0.9333333333333333




```python
#3grp discrminant analysis
Y=dataset.AmountSpentonFamilyVacation
```


```python
X=dataset[['AnnualFamilyIncome', 'AttitudeTowardTravel',
       'ImportanceAttachedtoFamilyVacatioin', 'HouseholdSize',
       'AgeofHeadofHousehold']]
```


```python
clf=LinearDiscriminantAnalysis()
```


```python
clf.fit(X,Y)
```




    LinearDiscriminantAnalysis()




```python
print(clf.predict(X))
```

    [2 3 3 1 2 3 2 2 3 3 3 3 2 2 3 1 1 2 2 1 1 2 2 1 1 2 2 1 1 1]
    


```python
clf.score(X,Y)
```




    0.8666666666666667




```python

```
