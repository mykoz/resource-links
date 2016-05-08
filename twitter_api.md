#Twitter API

#### Table of Contents
[A)  Sign up for Twitter Account](#section-a)  
[B)  Obtain Twitter API Credentials](#section-b)  
[C)  Set up Local Configuration File](#section-c)  
   
---

## <a name="section-a"></a>A) Sign up for Twitter Account  

[Twitter.com](https://twitter.com/)

---

## <a name="section-b"></a>B) Obtain Twitter API Credentials 

[Twitter API Tutorial (last updated 28Feb2016)](http://socialmedia-class.org/twittertutorial.html)  

Application Details  
Name:  ds7_twitter
Description:  Twitter Example for Cohort 7  
Website:  http://www.reshama.nyc  (even though it no longer exists)  


(Note:  You will need to add a mobile phone to your account to get access to API.)


---

## <a name="section-c"></a>C) Set up Local Configuration File

Tokens and keys should be kept in `.twitter_config` file.  (Tokens and keys are variables that contains the user credentials to access Twitter API.)

> Checking to see if I have a config file.  If not, I will create one.
```bash
reshama$ pwd
/Users/reshamashaikh
reshama$ ls .twitter_config 
ls: .twitter_config: No such file or directory
reshama$ 
``` 

####Add in your Twitter API credentials using below format
**Note:  these are my credentials.  They won't work on your computer.**  

```bash
reshama$ cat > ~/.twitter_config << END
{
 "consumer_key": "1h3Ncr6xWXXn0TtmNmDQP06mFP",
 "consumer_secret": "9LL1dgFgmGD3sSm8fOZEoMlY4yJ5PFJG1CaNBI2eNSB3jfNwJk",
 "access_token": "49013575-cR7uawlCRvifDEt9u8wFOK2Ir48xc7PDNB14gSmDy",
 "access_token_secret": "0cmGhiyvmdnguKiUMVs17KiJAYo1ESu4zCIwNynl9n132"
}
END
```

Verify that the `.twitter_config` file is there
```bash
reshama$ cat .twitter_config
{
 "consumer_key": "1h3Ncr6xWXXn0TtmNmDQP06mFP",
 "consumer_secret": "9LL1dgFgmGD3sSm8fOZEoMlY4yJ5PFJG1CaNBI2eNSB3jfNwJk",
 "access_token": "49013575-cR7uawlCRvifDEt9u8wFOK2Ir48xc7PDNB14gSmDy",
 "access_token_secret": "0cmGhiyvmdnguKiUMVs17KiJAYo1ESu4zCIwNynl9n132"
}
reshama$ 
```


