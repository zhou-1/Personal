collections is a built-in module.     


## Counter()    
It is a basic counter, for example, count for the number of appearence of character.     

    >>> from collections import Counter
    >>> c = Counter()
    >>> for ch in 'programming':
    ...     c[ch] = c[ch] + 1
    ...
    >>> c
    Counter({'g': 2, 'm': 2, 'r': 2, 'a': 1, 'i': 1, 'o': 1, 'n': 1, 'p': 1})


## defaultdict()     
when key doesn't exist, if we visit dictionary by key, it will have 'keyError'. In case to avoid this, we use defaultdict() to provide default value. If key exist, provide the value; if doesn't, provide none.     

    cntr_lp, res = collections.defaultdict(int), None


## namedtuple
If we need a tuple to mark a coordinate    

    from collections import namedtuple

https://www.liaoxuefeng.com/wiki/1016959663602400/1017681679479008



