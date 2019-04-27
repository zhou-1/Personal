boolean is the type of basic data

Boolean is the wrapper class of boolean, it has attributes and way, can use new.     
For example, Boolean flag = new Boolean("true");  // boolean cannot use like this.       
The only way can use Boolean is getting value from list and Hash table.   
i.e.  boolean t = false; Map map = new HashMap(); map.put("t", t);
then when we need to get the value, we use Boolean t1 = (Boolean) map.get(t); //previously, we cna only use Boolean to transfer by force, cannot use boolean     

