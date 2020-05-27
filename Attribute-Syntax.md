With sufficent examples, you should be able to interpret the attribute syntax. There is no big secret behind it, everyone who takes a brief look at it should gain sufficient understanding. You may want to read up on [EvalEx](https://github.com/uklimaschewski/EvalEx) to unearth the utmost out of the computing capacity.

# Examples that are WORKING

How to add a flat amount to something
> ADD 158 TO SHIELD_AMOUNT

How to raise something by 30% in total
> ADD 10% TO SHIELD_AMOUNT  
> ADD 15% TO SHIELD_AMOUNT  
> ADD 5% TO SHIELD_AMOUNT  

How to multiply the result with 2*3*1.5=9
> ADD 100%% TO SHIELD_AMOUNT  
> ADD 200%% TO SHIELD_AMOUNT  
> ADD 50%% TO SHIELD_AMOUNT  

How to raise regeneration (percent based) by 1%
> ADD 0.01 TO HEALTH_PERCENT

How to lower something by 5% per level
> REMOVE 5*SELF_LEVEL% OF SHIELD_AMOUNT

How to use create diminishing gains
> ADD SQRT(SELF_LEVEL)% TO SHIELD_AMOUNT

# Examples that are NOT WORKING

Will not work due to missing parts
> 5% SHIELD_AMOUNT

Will not work due to incorrect parts
> PLUS 13% @ HEALTH_AMOUNT

Will not work due to mangled math
> ADD 13+(1% TO SHIELD_AMOUNT

Will not work due to unfamiliar attribute
> ADD 10 TO SHIIIELLDDDD_AMOUNNDD