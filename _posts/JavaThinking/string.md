# string    

## string.replace & string.replaceAll()    

    string.replace(String str1,String str2); //use str2 to replace of str1         
    string.replaceAll(String regex, String replacement); //regex is regular rxpression, defines a search pattern for strings. replacement is used for replace the thing said in regex.       
    //i.e.     
    S.replaceAll("[^" + J + "]", "").length();  //use "" replace of (any character except character in string J) in string S     


## regular expression    
Common matching symbols
1 .      
Matches any character       
2 ^regex   
Finds regex that must match at the beginning of the line.    
3 regex$     
Finds regex that must match at the end of the line.      
4 [abc]     
Set definition, can match the letter a or b or c.     
5 [abc][vz]    
Set definition, can match a or b or c followed by either v or z.     
6 [^abc]     
When a caret appears as the first character inside square brackets, it negates the pattern. This pattern matches any character except a or b or c.      
7 [a-d1-7]     
Ranges: matches a letter between a and d and figures from 1 to 7, but not d1.     
8 X|Z      
Finds X or Z.      
9 XZ    
Finds X directly followed by Z.      
10 $    
Checks if a line end follows.       

https://www.vogella.com/tutorials/JavaRegularExpressions/article.html     


## String.valueOf()    
Convert basic data type to String, it is a static method.    

    String.valueOf(int i) //combert int to string


