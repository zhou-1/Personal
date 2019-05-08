# Hash Set   
Not the construction of key-value, only store the elements not same, we can say HashSet as basic HashMap only keeps the key.    
Creating ways:    
HashSet<Integer> set = new HashSet<Ineteger>(nums.length);     


# Hash Map    
Not ensure thread safe. Can use null as key. Initial volume is 16.        
Array + Linked list        
Creating ways:   
HashMap<Character, Integer> HM = new HashMap<Character, Integer>(); //need to mark type in <>    
HashMap HM = new HashMap(); //no need for clarifying type    
<b>HashMap.containsKey() method </b> is used for checking whether specified key map to HashMap, it uses key element as parameter, if element can map in hashmap, it will return true. i.e. hash_map.put(30, "You"); 30 is the key.    
<b>HashMap.getOrDefault(value, defaultValue) </b> method which can use the key value when Map collection contains key, otherwise use default value which normally is 0.    




# Hash Table    
Use synchronized to ensure thread safe. Cannot use null as key. Initial volume is 11.     
Array + Linked list    


HashMap & HashTable    
same: both of them store key-value   
difference: default initial volume is different, Map is 16, Table is 11; Hashtable is thread-safe, HashMap is not; HashTable allows the key be empty, HashMap allows the key and value be empty; the way iterating is different, HashMap is from front to back, then iterate from the start from the beginning  of specific linked list of array; HashTable is from back to front, then iterate from the start from the beginning  of specific linked list of array.     


