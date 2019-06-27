# Heap    
堆是一种树，由它实现的优先级队列的插入和删除的时间复杂度都是O(logn)，用堆实现的优先级队列虽然和数组实现相比较删除慢了些，但插入的时间快的多了。当速度很重要且有很多插入操作时，可以选择堆来实现优先级队列      

      PriorityQueue<Integer> heap = new PriorityQueue<> ((n1, n2) -> n1 - n2);
      //comparator written in lambda expression, which specifies how the n1 n2 should compare it's elements. 
      //In this case, the expression means the n1 n2 should give priority to the number whose value is smaller.
      //So, bigger value in the bottom, smaller element on the top

      ((a,b) -> (a.equals(b) ? a.compareTo(b) : a-b);
      //a.compareTo(b): give priority to smaller value in alphabetical order, a > b, so  store a first     
      //a - b: give priority to smaller value, in list, store 1 first; in heap, 2 in bottom, 1 on top.      


poll是队列数据结构实现类的方法，从队首获取元素，同时获取的这个元素将从原队列删除          
remove() 和 poll() 方法都是从队列中删除第一个元素。remove() 的行为与 Collection 接口的版本相似，但是新的 poll() 方法在用空集合调用时不是抛出异常，只是返回 null。因此新的方法更适合容易出现异常条件的情况。     

offer是往队列的前端加入元素     
一些队列有大小限制，因此如果想在一个满的队列中加入一个新项，多出的项就会被拒绝。这时新的 offer 方法就可以起作用了。它不是对调用 add() 方法抛出一个 unchecked 异常，而只是得到由 offer() 返回的 false。       

peek用于在队列的头部查询元素       
element() 和 peek() 用于在队列的头部查询元素。与 remove() 方法类似，在队列为空时， element() 抛出一个异常，而 peek() 返回 null        

