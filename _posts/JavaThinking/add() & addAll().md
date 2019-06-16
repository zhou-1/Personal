# .add()
add是将传入的参数作为当前List中的一个Item存储，即使你传入一个List也只会另当前的List增加1个元素      

    add(int index,Elelemt e)



# .ddAll()    
是传入一个List，将此List中的所有元素加入到当前List中，也就是当前List会增加的元素个数为传入的List的大小    

    addAll(Collection c)   

此方法按照指定 collection 的迭代器所返回的元素顺序，将该 collection 中的所有元素添加到此列表的尾部。如果正在进行此操作时修改指定的 collection ，那么此操作的行为是不确定的。（这意味着如果指定的 collection是此列表且此列表是非空的，那么此调用的行为是不确定的）。      

如果有多个已经被实例化的List 集合，想要把他们组合成一个整体，并且，这里必须直接使用List 自身提供的一个方法List.addAll()，否则使用了List.add()方法，则会输出不正常的信息     



