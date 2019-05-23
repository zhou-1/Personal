# Queue interface and List, Set are in same level，all of them inherits Collection interface.   

## 1. List    

### ArrayList    
It is created by array, it is kind of like array but can change the size.    

    ArrayList<Integer> arrayList = new ArrayList<Integer>();
    
visit element complexity: O(1); add/delete element complecity: O(n)     

### LinkedList    
It is created by two-directed linked list.       
Compare with ArrayList, it is quicker at add and delte, slower at query and modify the value.     

    LinkedList<Integer> linkedList = new LinkedList<Integer>();

<b> linkedList.add() </b> add one new node to end of the linked list.    
<b> linkedList.addFirst() </b> add one new node to start of the linked list.     
<b> linkedList.clear() </b> loop through items, free all of the elemnts, set all of previous an dnext pointer to null.     
<b> linkedList.get(int index) </b> get the node at the pointed place        
<b> linkedList.contains() </b> return the length of linked list/number of nodes     

visit element complexity: O(n); add/delete element complecity: O(1)

There are linked list nodes inside, they have attributes to visit previous(.prev), current(.item) and next node(.next). 


## 2. queue    
A First-In-First-Out data structure. It is created by LinkedList.         

    Queue<Employee> queue = new LinkedList<>();

Methods:    
add        
add an element                                           If queue is full, throw out IIIegaISlabEepeplian      
remove     
remove and return element at begin/head of the queue     If queue is empty, throw out NoSuchElementException    
element    
return element at the head of the queue                  If queue is empty, throws out NoSuchElementException     
offer      
add an element and return true                          If queue is full, return false    
poll      
remove and return the element at head of the queue       If queue is empty, return null       
peek       
return element at head of the queue                      If queue is empty, return nul    
put        
add an element                                           If queue is full, then block    
take       
remove and return the element at head of the queue       If queue is empty, then block       

remove、element、offer 、poll、peek belongs to Queue interface.       


## 3. Set     
Set has HashSet and TreeSet, do not allow duplicates inside and elements inside are random.       

Methods:     
add( )         add elements to set       	
clear( )       remove all of the elements of set       	
contains( )    determine whether the set contain one element or nor     	
isEmpty( )     determin whether the set is empty      
iterator( )    mainly used for iteration, returns a Iterator() object        
remove( )      remove specified object from the set      
size( )        return the size of the set         



