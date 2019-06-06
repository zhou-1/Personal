collections is a built-in module.     


## Counter()    
It is a basic counter, for example, count for the number of appearance of character.     

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

语法格式： 

    collections.defaultdict([default_factory[, …]])

该函数返回一个类似字典的对象。defaultdict是Python内建字典类（dict）的一个子类，它重写了方法_missing_(key)，增加了一个可写的实例变量default_factory,实例变量default_factory被missing()方法使用，如果该变量存在，则用以初始化构造器，如果没有，则为None。其它的功能和dict一样。    
第一个参数为default_factory属性提供初始值，默认为None；其余参数包括关键字参数（keyword arguments）的用法，和dict构造器用法一样。     


## namedtuple
If we need a tuple to mark a coordinate    

    from collections import namedtuple

https://www.liaoxuefeng.com/wiki/1016959663602400/1017681679479008



