# Queue interface and List, Set are in same level，all of them inherits Collection interface.   

## List    

### ArrayList    
It is created by array, it is kind of like array but can change the size.    

    ArrayList<Integer> arrayList = new ArrayList<Integer>();


### LinkedList    
It is created by two-directed linked list.       
Compare with ArrayList, it is quicker at add and delte, slower at query and modify the value.     

    LinkedList<Integer> linkedList = new LinkedList<Integer>();

<b> linkedList.add() </b> add one new node to end of the linked list.    
<b> linkedList.addFirst() </b> add one new node to start of the linked list.     
<b> linkedList.clear() </b> loop through items, free all of the elemnts, set all of previous an dnext pointer to null.     
<b> linkedList.get(int index) </b> get the node at the pointed place        
<b> linkedList.contains() </b> return the length of linked list/number of nodes     

## Queue    
A First-In-First-Out data structure. It is created by LinkedList.         

    Queue<Employee> queue = new LinkedList<>();

add        add an element                                           If queue is full, throw out IIIegaISlabEepeplian     
remove     remove and return element of begin/head of the queue     If queue is empty, throw out NoSuchElementException    
element    返回队列头部的元素             如果队列为空，则抛出一个NoSuchElementException异常
offer      添加一个元素并返回true       如果队列已满，则返回false
poll       移除并返问队列头部的元素    如果队列为空，则返回null
peek       返回队列头部的元素             如果队列为空，则返回null
put        添加一个元素                      如果队列满，则阻塞
take       移除并返回队列头部的元素     如果队列为空，则阻塞

remove、element、offer 、poll、peek belongs to Queue interface.       





