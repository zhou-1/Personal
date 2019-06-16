## Queue    
First in First out.    
Based on LinkedList, only allows delete process on front of list, add process on end of the list.    

add()       增加一个元索                     如果队列已满，则抛出一个IIIegaISlabEepeplian异常    

remove()   移除并返回队列头部的元素    如果队列为空，则抛出一个NoSuchElementException异常   

element()  返回队列头部的元素             如果队列为空，则抛出一个NoSuchElementException异常    

offer()       添加一个元素并返回true       如果队列已满，则返回false   

poll()         移除并返问队列头部的元素    如果队列为空，则返回null   

peek()       返回队列头部的元素             如果队列为空，则返回null    

put()        添加一个元素                      如果队列满，则阻塞   

take()        移除并返回队列头部的元素     如果队列为空，则阻塞    

boolean isEmpty() 判断队列是否为空   

size() 返回队列长度     

时间复杂度分析：    
O(1) Push / O(1) Pop / O(1) Top      


## Stack    
boolean empty() 测试堆栈是否为空     

Object peek() 查看堆栈顶部的对象，但不从堆栈中移除它         

Object push() 把项压入堆栈顶部            

Object pop() 栈结构的实现类的方法，表示返回栈顶的元素，同时该元素从栈中删除，当栈中没有元素时，调用该方法会发生异常          


时间复杂度：    
O(1) Push / O(1) Pop / O(1) Top     



## Heap     
Heap 是一种二叉树(binary tree), 说得再准确一点, 它是一种完全二叉树(complete binary tree)     
最小堆：父结点的值小于两个左右结点的值；最大堆：父结点的值大于两个左右结点的值    

PriorityQueue      
默认为最小堆，可以用比较器构造最大堆     

    PriorityQueue<Integer> heap = new PriorityQueue<> ((n1, n2) -> n1 - n2);
    //comparator written in lambda expression, which specifies how the n1 n2 should compare it's elements. 
    //In this case, the expression means the n1 n2 should give priority to the number whose count is greater.
    //So, bigger value in the bottom, smaller element on the top

poll() 队列数据结构实现类的方法，从队首获取元素，同时获取的这个元素将从原队列删除        




