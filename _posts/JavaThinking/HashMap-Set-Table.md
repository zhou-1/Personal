# Hash Set   
Not the construction of key-value, <b> only store the elements not same </b> , we can say HashSet as basic HashMap only keeps the key.    
Creating ways:    

     HashSet<Integer> set = new HashSet<Ineteger>(nums.length);     
Or we do not have to mention type of data, then we can use mixed types.    

     Set seen = new HashSet();  


# Hash Map    
Not ensure thread safe. Can use null as key. Initial volume is 16.       
<b> cannot store the same elements as key </b>    
Array + Linked list        
Creating ways:   

     HashMap<Character, Integer> HM = new HashMap<Character, Integer>(); //need to mark type in <>    
     HashMap HM = new HashMap(); //no need for clarifying type      

<b>HashMap.keySet() </b> get all of the key of Map, it actually returns a set of all keys.     
<b>HashMap.entrySet() </b> 返回Map 中的一个实体（一个key-value对），也是一个Set集合；接口中有getKey(),getValue方法      

     //第三种：推荐，尤其是容量大时  
     System.out.println("通过Map.entrySet遍历key和value");  
     for (Map.Entry<String, String> entry : map.entrySet()) {  
          System.out.println("key= " + entry.getKey() + " and value= " + entry.getValue());  
     }  

<b>HashMap.values() </b> get all of the value of Map, it actually returns a collection of all values.           
<b>HashMap.put(key, value) </b> insert mapping into mapping. We can have new value instead of previous value; if we pass one new key and value pair, they will be new.      
<b>HashMap.containsKey() method </b> is used for checking whether specified key map to HashMap, it uses key element as parameter, if element can map in hashmap, it will return true. i.e. hash_map.put(30, "You"); 30 is the key.    
<b>HashMap.getOrDefault(value, defaultValue) </b> method which can use the key value when Map collection contains key, otherwise use default value which normally is 0.     
<b>HashMap<Character, Integer> charMap = (HashMap<Character, Integer>)map.clone() [map is what we need clone from] / charMap.putAll(map) </b> deep clone from map to charMap. If we modify the elements, both of them will change; but if we add/delete elements, each of them will change its own.      

## Hash Collision    
HashMap is using Hash Algorithm to determine the store place of each element, every Java object can use hashCode() method to get the value of hash code. Based on this hash code, system determines the place. <b> But if the place has already placed by other element(s), </b> it is called hash collision.      
Hash map in java is using one-way linked list to solve this problem.      
<b> Load factor and Threshold attributes </b> of Hash Map:    
Load Factor stands for how many elements in hash map, if it is bigger, the rate of using space is higher, the chance of hash collision is higher but the efficiency of search is lower; if it is smaller, the rate of using space is lower, the chance of hash collision is lower but the efficiency of search is higher; so we need a balance, default is good, 0.75.     
Threshold is size of hash map * load factor; if actual size of hash map is bigger than threshold, we need to resize (make it bigger) the hash map.      
[More details](https://www.cnblogs.com/peizhe123/p/5790252.html)    

## Iterate HashMap     
Use iterator()    

     Map map = new HashMap();   
     Iterator iter = map.entrySet().iterator();   
      while (iter.hasNext()) {   
          Map.Entry entry = (Map.Entry) iter.next();   
          Object key = entry.getKey();   
          Object val = entry.getValue();   
      }   

 


# Hash Table    
Use synchronized to ensure thread safe. Cannot use null as key. Initial volume is 11.     
Array + Linked list    



## HashMap & HashTable    
same: both of them store key-value   
difference: 
Hashtable is "older" than HashMap, but few people using it now.    
Hashtable is from Dictionary class, Hashmap is from AbstractMap class.    
Default initial volume is different, Hashtable is 11, Hashmap is 16.    
Every time later it dilatates, Hashtable will become (2n + 1) of original, Hashmap will become (2n).     
Hashtable is thread-safe which makes low-efficient, HashMap is not.       
Hashtable allows the key be empty, HashMap allows the key and value be empty.      
Hashtable doesn't support Null key or Null value, HashMap can have one Null key and Null values.    
The way iterating is different, HashMap is from front to back, then iterate from the start from the beginning  of specific linked list of array; HashTable is from back to front, then iterate from the start from the beginning  of specific linked list of array.      



