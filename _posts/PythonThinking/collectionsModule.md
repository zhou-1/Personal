collections is a built-in module.     

## namedtuple
If we need a tuple to mark a coordinate    

    from collections import namedtuple

https://www.liaoxuefeng.com/wiki/1016959663602400/1017681679479008


## defaultdict()     
when key doesn't exist, if we visit dictionary by key, it will have 'keyError'. In case to avoid this, we use defaultdict() to provide default value. If key exist, provide the value; if doesn't, provide none.     

    cntr_lp, res = collections.defaultdict(int), None


