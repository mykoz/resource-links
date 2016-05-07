

```
#bin Release Dates by month
movies['RD_month']=pd.DatetimeIndex(movies['ReleaseDate']).month
```

```
# extract month from datetime64
mv_df['month'] =  pd.DatetimeIndex(mv_df['reldate']).month
print mv_df[:2] 
```

Time saving tip (and cleaner code): Use the following to generate a list of month abbreviations for xticks (or anywhere else)  
`list(calendar.month_abbr)[1:]`
