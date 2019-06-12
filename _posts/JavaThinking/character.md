# character    

### Character.isLetter() / Character.isDigit() / Character.isWhitespace()      
result is boolean value: true/false; first is for letter, second is for digits, third is for white space.        

### Character.isUpperCase()/.isLowerCase()     
result is boolean value; check for upper case or lower case.      

### Character.toUpperCase()/.toLowerCase()/toString()      
change to upper case/lower case/ string type but with length of only 1.      

### character to int      
String.valueOf(): change character to String first    
Integer.parseInt(): change string to int    

    String a = '123';
    int c = Integer.parseInt(String.valueOf(a.charAt(i)));

