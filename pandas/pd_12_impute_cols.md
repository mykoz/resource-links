
```
representatives = representatives.replace('y',1)
representatives = representatives.replace('n',0)
representatives = representatives.replace('?',np.nan)

#replace ? values with the column mean
for column in range(1,17):
    colmean = representatives[column].mean()
    representatives.loc[np.isnan(representatives[column]), column] = colmean

representatives.head()

```

