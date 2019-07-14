### I) 1118. Number of Days in a Month        
Given a year Y and a month M, return how many days there are in that month.     

Example 1:     
Input: Y = 1992, M = 7   
Output: 31    

Example 2:    
Input: Y = 2000, M = 2   
Output: 29    

Example 3:    
Input: Y = 1900, M = 2   
Output: 28    

Note:    
1583 <= Y <= 2100    
1 <= M <= 12     

My thoughts and code: https://leetcode.com/problems/number-of-days-in-a-month/discuss/334154/Understanding-is-most-difficult-part-in-this-question       

Same idea but less code    

    public int numberOfDays(int Y, int M) {
        int[] days = new int[]{31,28,31,30,31,30,31,31,30,31,30,31};
        if((Y%4==0 && Y%100!=0) || Y%400==0) days[1] = 29;
        return days[M-1];
    }


use java.time.YearMonth      
    
    public int numberOfDays(int Y, int M) {
        return java.time.YearMonth.of(Y, M).lengthOfMonth();
    }




### II) 1119. Remove Vowels from a String        
Given a string S, remove the vowels 'a', 'e', 'i', 'o', and 'u' from it, and return the new string.      

Example 1:    
Input: "leetcodeisacommunityforcoders"    
Output: "ltcdscmmntyfrcdrs"    

Example 2:     
Input: "aeiou"    
Output: ""    
 
Note:    
S consists of lowercase English letters only.     
1 <= S.length <= 1000    


My solution
I. StringBuilder for every element
      
      public String removeVowels(String S) {
        //prepare for result
        String res = "";
        
        //check for extreme condition
        if(S == null || S.length() == 0){
            return res;
        }
        
        StringBuilder SB = new StringBuilder();
        
        for(int i = 0; i < S.length(); ++i){
            if(S.charAt(i) == 'a' || S.charAt(i) == 'e' || S.charAt(i) == 'i' || S.charAt(i) == 'o' || S.charAt(i) == 'u'){
                SB.append("");
            }    
            else{
                SB.append(S.charAt(i));
            }
        }
        
        res= SB.toString();
        return res;
        
    }

II. easy method with replace()    

    public String removeVowels(String S) {
        //prepare for result
        String res = S;
        
        res = res.replace("a", "");
        res = res.replace("e", "");
        res = res.replace("i", "");
        res = res.replace("o", "");
        res = res.replace("u", "");
        
        return res;
        
    }

III. replaceAll()    

    public String removeVowels(String S) {
        return S.replaceAll("[a,e,i,o,u]", "");
    }


### III) 1120. Maximum Average Subtree      
Given the root of a binary tree, find the maximum average value of any subtree of that tree.    
(A subtree of a tree is any node of that tree plus all its descendants. The average value of a tree is the sum of its values, divided by the number of nodes.)     

Example 1:       
![Explain Image1](img/Bi-contest1-III-0.png )    





