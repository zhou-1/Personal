==: compares for the address of object, check whether it points out to same object    

equal(): compares value of object    

i.e.      
Integer r1 = new Integer(900);//define int object of r1   
Integer r2 = new Integer(900);//define int object of r2   
System.out.println(r1==r2);//return false   
System.out.println(r1.equal(r2));//return true     

i.e.  
a and b points out to same address and value is "hello"    
c points out to another address and value is "hello"    
a == b  //true    
a == c  //false   
a.equals(c)  //true   

