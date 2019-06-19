# Queue interface and List, Set are in same level，all of them inherits Collection interface.   

## 1. List    
In list, elements can be duplicates but in add-in order.      

### ArrayList    
It is created by array, it is kind of like array but can change the size.    

    ArrayList<Integer> arrayList = new ArrayList<Integer>();
    
visit element complexity: O(1); add/delete element complecity: O(n)    

#### Iterator    

    public static void remove(ArrayList<String> list) 
    {
        Iterator<String> it = list.iterator();
        while (it.hasNext()) 
        {
            String s = it.next();
            if (s.equals("b")) 
            {
                it.remove();
            }
        }
    }

#### .set    
public E set(int index, E element) index -- 替换索引的元素;element -- 要被存储在指定位置的元素.       

    arrlist.add(15);
    arrlist.add(20);
    arrlist.add(25);
    arrlist.add(22);

    // inserting elment 55 at 3rd position
    arrlist.set(2,55);
    
    //answer for new list
    Number = 15
    Number = 20
    Number = 55
    Number = 22

#### Iterate elements to delete/remove one element
1. 不要使用ArrayList的remove，改为用Iterator的remove即可；单纯地使用for(String: list) 这种foreach 写法是对实际的Iterable、hasNext、next方法的简写， 会造成并发修改异常：java.util.ConcurrentModificationException        

        public static void remove(ArrayList<String> list) 
        {
            Iterator<String> it = list.iterator();
            while (it.hasNext()) 
            {
                String s = it.next();
                if (s.equals("b")) 
                {
                    it.remove();
                }
            }
        }

2. 对数组进行倒序遍历；即使发生元素删除也不影响后序元素遍历。因为正序遍历（list.get(inti=0;i<list.size();i++)）时，在遍历第一个字符串b时因为符合删除条件，所以将该元素从数组中删除，并且将后一个元素移动（也就是第二个字符串b）至当前位置，导致下一次循环遍历时后一个字符串b并没有遍历到，所以无法删除         

        public static void remove(ArrayList<String> list)
        {
            for(inti=list.size()-1;i>=0;i--)
            {
                Strings=list.get(i);
                if(s.equals("b"))
                {
                    list.remove(s);
                }
            }
        }

3. 交换要删除的元素和最后一个元素。然后remove “现有的最后一个元素”即可。     

        int loc = map.get(val);
        if (loc < nums.size() - 1 ) { // not the last one than swap the last one with this val
            int lastone = nums.get(nums.size() - 1 );
            nums.set( loc , lastone ); //nums:ArrayList    
            map.put(lastone, loc);
        }
        map.remove(val);
        nums.remove(nums.size() - 1);



### LinkedList    
It is created by two-directed linked list.       
Compare with ArrayList, it is quicker at add and delte, slower at query and modify the value.     

    LinkedList<Integer> linkedList = new LinkedList<Integer>();

Good for processing data for several times.    

<b> linkedList.add() </b> add one new node to end of the linked list.    
<b> linkedList.addFirst() </b> add one new node to start of the linked list.     
<b> linkedList.clear() </b> loop through items, free all of the elemnts, set all of previous an dnext pointer to null.     
<b> linkedList.get(int index) </b> get the node at the pointed place        
<b> linkedList.contains() </b> return the length of linked list/number of nodes     

visit element complexity: O(n); add/delete element complecity: O(1)

There are linked list nodes inside, they have attributes to visit previous(.prev), current(.item) and next node(.next). 
<b> ListNode </b> we can also build this:     

    final ListNode[] nodes = new ListNode[10000];  


## 2. queue    
A First-In-First-Out data structure. It is created by LinkedList.         

    Queue<Employee> queue = new LinkedList<>();

Good for processing data once.   

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


## 4. Stack    
A Last-In-First-Out structure. Can only add/remove element at one end. It is created by Array.      
In java, it is a function without parameters.    

    Stack<Integer> stack = new Stack<> ();

Methods:
push();  //add element    
pop();  //remove element from stack
empty() //determine stack is empty or not
peek() //get element from top of stack
search(x) //determin element x in stack or not; if so, return 1; else, return -1       
pop() will pop element out of stack and return the element; peek() will just get the value.     



