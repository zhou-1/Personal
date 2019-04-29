int is a type of primitive/basic data. (all: boolean, character, byte, short, long, integer, float, double)       
int directly store the value of data.   
Default value of int is 0.       


Integer is the wrapper class of int. Integer can only be used after instantiation.    
Integer actually is used for object, when we new a Integer, it generates a pointer to object.    
Default value of Integer is null.    
Used for reference type, key and value in HashMap are both object which means reference type    
<b> Integer can distinguish value is 0 or not give the value. </b> i.e., if we want to express the difference between not attend to exam and score of exam is 0. 

Integer Pool.   
It caches the whole int objects in the range of -128 ~ 127     
Integer i = value. If i is in the range of -128 ~ 127, we will not create object in heap, returns value in IntegerCache directly; if not in the range, it creats object from heap.    
Integer i2 = new Integer(xxxx), no matter the value of xxxx, it creates object directly from heap.   


Pool   
advantage: save memory, save running time (== is faster than equals()).    
  
