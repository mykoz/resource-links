
>     Add Rule:  select 'Custom TCP Rule'
      Port Range: 5432  (for PostgreSQL)
      Source:  Anywhere


to not lose your terminal connection to AWS when your computer goes to sleep, add line to your .ssh/config file
```
Host *
  ServerAliveInterval 60

```
