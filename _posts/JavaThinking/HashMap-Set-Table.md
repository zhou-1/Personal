# Hash Map    
Not ensure thread safe. Can use null as key. Initial volume is 16.       
Array + Linked list      
<b>HashMap.containsKey() method </b> is used for checking whether specified key map to HashMap, it uses key element as parameter, if element can map in map, it will return true. i.e. hash_map.put(30, "You"); 30 is the key.    
Creating ways:   
HashMap<Character, Integer> HM = new HashMap<Character, Integer>(); //need to mark type in <>    
HashMap HM = new HashMap(); //no need for clarifying type    



# Hash Table    
Use synchronized to ensure thread safe. Cannot use null as key. Initial volume is 11.     
Array + Linked list    


# Hash Set   
Not the construction of key-value, only store the elements not same, we can say HashSet as basic HashMap only keeps the key.    
Creating ways:    
HashSet<Integer> set = new HashSet<Ineteger>(nums.length);     

