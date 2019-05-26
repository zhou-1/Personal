Used for compare with same kinds of object.     

    public int compareTo( NumberSubClass referenceName )
    
If pointed number same to parameter, return 0;     
If less, return -1;    
If bigger, return 1.    

    public class Test{ 
    public static void main(String args[]){
      Integer x = 5;
      System.out.println(x.compareTo(3));
      System.out.println(x.compareTo(5));
      System.out.println(x.compareTo(8));            
     }
    }

   Result will be:    
   1   
   0   
  -1      
