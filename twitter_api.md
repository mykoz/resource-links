##Twitter API

####Set up configuration file
Tokens and keys should be kept in `.twitter_config` file.  (Tokens and keys are variables that contains the user credentials to access Twitter API.)

> Checking to see if I have a config file.  If not, I will create one.
```bash
reshama$ pwd
/Users/reshamashaikh
reshama$ ls .twitter_config 
ls: .twitter_config: No such file or directory
reshama$ 
```

```console
cat > ~/.twitter_config << END
[default]
access_token='49013575-cR7uawlCRvifDEt9u8wFOK2Ir48xc7PDNB14gSmDy'
access_token_secret='0cmGhiyvmdnguKiUMVs17KiJAYo1ESu4zCIwNynl9n132'
consumer_key='h3Ncr6xWXXn0TtmNmDQP06mFP'
consumer_secret='9LL1dgFgmGD3sSm8fOZEoMlY4yJ5PFJG1CaNBI2eNSB3jfNwJk'
END
```

```console
cat > ~/.twitter_config << END
access_token='49013575-cR7uawlCRvifDEt9u8wFOK2Ir48xc7PDNB14gSmDy'
access_token_secret='0cmGhiyvmdnguKiUMVs17KiJAYo1ESu4zCIwNynl9n132'
consumer_key='h3Ncr6xWXXn0TtmNmDQP06mFP'
consumer_secret='9LL1dgFgmGD3sSm8fOZEoMlY4yJ5PFJG1CaNBI2eNSB3jfNwJk'
END
```



Verify that the `.twitter_config` file is there
```console
reshama$ cat .twitter_config
[default]
oauth_token= '49013575-cR7uawlCRvifDEt9u8wFOK2Ir48xc7PDNB14gSmDy'
oauth_secret= '0cmGhiyvmdnguKiUMVs17KiJAYo1ESu4zCIwNynl9n132'
consumer_key= 'h3Ncr6xWXXn0TtmNmDQP06mFP'
consumer_secret= '9LL1dgFgmGD3sSm8fOZEoMlY4yJ5PFJG1CaNBI2eNSB3jfNwJk'
reshama$ 
```




[Twitter API Tutorial (last updated 28Feb2016)](http://socialmedia-class.org/twittertutorial.html)  

Application Details  
Name:  ds7_twitter
Description:  Twitter Example for Cohort 7  
Website:  http://www.reshama.nyc  (even though it no longer exists)  


(Note:  You will need to add a mobile phone to your account to get access to API.)


