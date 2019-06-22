# Loop    

### For Loop     
In for loop below, i will be 0 to 9.    

    for(int i = 0; i<10; i++) {
      System.out.println(i);
    }

equals to:   

    for(int i=0; i<10;)
    {
      System.out.println(i);
      i++;
    }

Note: In for loop, ++i same to i++.     

Another way for loop     

    int[] integers = {1, 2, 3, 4};
    for(int i : integers){}   

### while Loop
while(循环条件){   

　　循环操作   

}    
while()括号里面有循环条件 如果循环条件返回为true 也就是满足循环条件那么就执行循环操作  否则 就不会执行循环操作      
但是使用这个循环一定要注意 如果条件永远成立的话那就就会死循环 如果出现这个情况就需要终止程序     
while循环的特点是先判断 在执行 如果判断结构返回的是错误 那么不会执行     

### do while loop      
do{     
    循环操作    
} while(循环条件);     
while 与 do while 循环 的不同点是 do -while循环是先执行一次 在判断  while循环是先判断在执行while循环是如果条件不成立一次都不执行      
do while循环是不管条件成不成立都先执行一次     


