
**Splitting the Data**  
If you can afford it, split the data 3 ways:
 * exploratory 
    * training (plot it, play, build models)
    * validation
    * (could later combine training + validation for info; open)
 * test

How to split
 * lots of data:  1/3, 1/3, 1/3
 * not too much data  
      * power  
      * sample size

---  

####Power & Sample Size Calculations

If you're stuck and not sure what you're doing, make some fake data and play with that.

---

####Power

Forming hypothesis  
H0: default action we are promising to execute when we know nothing; promise to do this if we don't learn anything  
H1:  

Does our evidence make the null hypothesis look like a ridiculous proposition?  

Example:  
H0:  not guilty  (Action:  go free)  (Learn:  nothing)   (Situation:  default)
H1:  guilty      (Action:  convict)  (Learn:  something) (Situation:  alternative)  

Power:  probability of rejecting null hypothesis when null hypothesis is false.  
**Power is your ability to learn something.**  

Two Errors:  
1.  Convict an innocent person (Type I Error)
2.  Let guilty person go free (Type II Error)

Type I Error  
Convict an innocent person.  
P(Type I Error) = P(Incorrectly rejecting the null hypothesis)  



Let a guilty criminal go free.  
P(Type II Error)   = P(incorrectly failing to reject the null hypothesis)
  = 1 - Power
 
 
 

