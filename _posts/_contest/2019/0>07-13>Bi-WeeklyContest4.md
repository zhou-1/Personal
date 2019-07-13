

### I) 1118. Number of Days in a Month        



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


