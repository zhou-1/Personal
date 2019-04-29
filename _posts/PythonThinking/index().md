Python index()    
detects whether string includes targeted str; we can also add begin and end range.    
This method is pretty similar to find(), but if str not includes in string, it will return an exception.    

i.e.   
 
str1 = "this is string example....wow!!!";   
str2 = "exam";   
print str1.index(str2);   
print str1.index(str2, 10);   
print str1.index(str2, 40);   

result:   
15   
15   
Traceback (most recent call last):   
  File "test.py", line 8, in    
  print str1.index(str2, 40);  
ValueError: substring not found   

shell returned 1   
