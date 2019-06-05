# array  
array is fixed once created. We cannot add/delete the length.     

    String[] strings = new String[size()];
    String[] s = {"a","b","c"};
    

## Cannot use .contains() in array     
Use for loop to determine each element; or use Arrays.asList(array), then use .contains()     

我们再来看看contains操作，可以看到实际调用的是indexOf方法。回到我们的代码中ints[i] 是int型（这里调用contains的时候自动打包成Integer类型，自动装箱）。所以再这个indexOf中比较时实际调用的是Integer.equals。    
由于我们初始化ArrayList的时候使用的是int[] ，所以在调用o.equals(a[i])的时候，传入的a[i]也是int型的。至此，obj instanceof Integer永远是false。所以在我们代码中，用Array.asList().contains判断某个数是否在数组中存在是不可行的。    
替代工具ArrayUtils：是common.lang中的一个方法类。 我们可以借助该类来确定一个数组中是否含有某个值。可以替换为ArrayUtils.contains(result,ints[i])    
原文：https://blog.csdn.net/syy19940213/article/details/80944681    


## Two-dimensional array       
int[][] arr = new int[3][5]; //An int-type two-dimensional array, includes 3 one-dimensional array and each can store 5 ints    
int[0] //first one-dimensional array    
int[1][3]  //forth element of second one-dimensional array      


## collection.toArray()   
If there is no parameter in list.toArray(), then the type of converted data is object[]     
We can cast Object[] to String[] if we use <b> list.toArray(new String[0]) </b>    
We can cast Object[] to int[] if we use <b> list.toArray(new int[0]) </b>     

## Arrays.copyof()    
copy the original array and be the length we need.    

    int[] copied = Arrays.copyOf(arr, 10); //10 the the length of the new array
    System.out.println(Arrays.toString(copied));
 
    copied = Arrays.copyOf(arr, 3);
    System.out.println(Arrays.toString(copied));

Result will be:    

    [1, 2, 3, 4, 5, 0, 0, 0, 0, 0]
    [1, 2, 3]

## Arrays.fill()   
fill the array, first parameter with value, second parameter.     

    int[] array = new int[26];
    Arrays.fill(array, 5); //array 数组中有26个5.   

## Arrays.asList()    
transfer array to list.     

type: int
     
    int[] datas = new int[]{1,2,3,4,5};
    List list = Arrays.asList(datas);
    System.out.println(list.size());
    //运行结果是1。一个长度为5的数组，转化为List后，长度却成了1。

type: Integer

    Integer[] datas = new Integer[]{1,2,3,4,5};
    List list = Arrays.asList(datas);
    System.out.println(list.size());

asList接受的是一个泛型类型的参数，再构造了一个ArrayList。然而基本类型是不支持泛型化的，但是数组支持，所以采用基本类型的数组转化后是将数组放入了构造的ArrayList中，长度是1     
We cnanot do modify operation on this list, if we want to, transfer this type of list to ava.util.ArrayList     

    Integer[] datas = new Integer[]{1,2,3,4,5};
    ArrayList<Integer> arrayList = new ArrayList<>(Arrays.asList(datas));










