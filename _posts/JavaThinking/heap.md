# Heap    
堆是一种树，由它实现的优先级队列的插入和删除的时间复杂度都是O(logn)，用堆实现的优先级队列虽然和数组实现相比较删除慢了些，但插入的时间快的多了。当速度很重要且有很多插入操作时，可以选择堆来实现优先级队列      

      PriorityQueue<Integer> heap = new PriorityQueue<> ((n1, n2) -> n1 - n2);
      //comparator written in lambda expression, which specifies how the n1 n2 should compare it's elements. 
      //In this case, the expression means the n1 n2 should give priority to the number whose count is greater.
      //So, bigger value in the bottom, smaller element on the top

poll是队列数据结构实现类的方法，从队首获取元素，同时获取的这个元素将从原队列删除    
      
