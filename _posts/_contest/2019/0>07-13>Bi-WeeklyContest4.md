

### 1119      

My solution    
      
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


