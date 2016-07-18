
>     Add Rule:  select 'Custom TCP Rule'
      Port Range: 5432  (for PostgreSQL)
      Source:  Anywhere


to not lose your terminal connection to AWS when your computer goes to sleep, add line to your .ssh/config file
```
Host *
  ServerAliveInterval 60

```
---

How to set up authentication so you can read and write to your AWS EC2 mongodb server (without granting admin priviledges to the whole internet) http://ianlondon.github.io/blog/mongodb-auth/
