# string builder    
String对象是不可改变的。每次使用 System.String类中的方法之一时，都要在内存中创建一个新的字符串对象，这就需要为该新对象分配新的空间。在需要对字符串执行重复修改的情况下，与创建新的 String对象相关的系统开销可能会非常昂贵。如果要修改字符串而不创建新的对象，则可以使用System.Text.StringBuilder类。例如，当在一个循环中将许多字符串连接在一起时，使用 StringBuilder类可以提升性能。    

    int[] count = new int[26];
    StringBuilder sb = new StringBuilder("");
    for (int i = 0; i < 26; i++) {
         sb.append('#');
         sb.append(count[i]);
    }

StringBuilder 类在 Java 5 中被提出，它和 StringBuffer 之间的最大不同在于 StringBuilder 的方法不是线程安全的（不能同步访问）。    
由于 StringBuilder 相较于 StringBuffer 有速度优势，所以多数情况下建议使用 StringBuilder 类。然而在应用程序要求线程安全的情况下，则必须使用 StringBuffer 类。     


## Append    
Append 方法可用来将文本或对象的字符串表示形式添加到由当前 StringBuilder对象表示的字符串的结尾处     

    StringBuilderMyStringBuilder = new StringBuilder("Hello World!");
    MyStringBuilder.Append(" What a beautiful day.");
    //Hello World! What abeautiful day.
    
## Insert    
Insert 方法将字符串或对象添加到当前 StringBuilder中的指定位置     

    StringBuilderMyStringBuilder = new StringBuilder("Hello World!");
    MyStringBuilder.Insert(6,"Beautiful ");
    //Hello BeautifulWorld!   

## delete(int start, int end);     
指定从哪删到哪     


## Replace    
Replace方法，可以用另一个指定的字符来替换 StringBuilder对象内的字符   

    StringBuilderMyStringBuilder = new StringBuilder("Hello World!");
    MyStringBuilder.Replace('!', '?');

    //Hello World?




