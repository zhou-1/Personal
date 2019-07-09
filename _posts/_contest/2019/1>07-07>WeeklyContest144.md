## Second try in contest.       

### I) 1108. Defanging an IP Address (easy)      
Given a valid (IPv4) IP address, return a defanged version of that IP address.      
A defanged IP address replaces every period "." with "[.]".      

Example 1:     
Input: address = "1.1.1.1"      
Output: "1[.]1[.]1[.]1"      

Example 2:     
Input: address = "255.100.50.0"     
Output: "255[.]100[.]50[.]0"    
 
Constraints:     
The given address is a valid IPv4 address.      


Solution:          
<b> Java </b>        
I. my solution    

    public String defangIPaddr(String address) {
        //prepare for result
        String res = null;
        
        //check for extreme condition
        if(address == null || address.length() <= 0){
            return res;
        }
        
        //SB for adding
        StringBuilder SB = new StringBuilder();
        
        //check for every element
        for(int i = 0; i < address.length(); ++i){
            if(address.charAt(i) != '.'){
                SB.append(address.charAt(i));
            }
            //it is '.'
            else{
                SB.append("[");
                SB.append('.');
                SB.append("]");
            }
        }
        
        res = SB.toString();
        return res;
    }

II. One line    

    public String defangIPaddr(String address) {
        return address.replace(".", "[.]");
    }


<b> Python </b>        

    def defangIPaddr(self, address: str) -> str:
        return address.replace('.', '[.]')



### II) 1109. Corporate Flight Bookings (medium)       
There are n flights, and they are labeled from 1 to n.     
We have a list of flight bookings.  The i-th booking bookings[i] = [i, j, k] means that we booked k seats from flights labeled i to j inclusive.     
Return an array answer of length n, representing the number of seats booked on each flight in order of their label.     

Example 1:    
Input: bookings = [[1,2,10],[2,3,20],[2,5,25]], n = 5    
Output: [10,55,45,25,25]    

Constraints:    
1 <= bookings.length <= 20000    
1 <= bookings[i][0] <= bookings[i][1] <= n <= 20000   
1 <= bookings[i][2] <= 10000      


Solution:       
<b> Java </b>     
I. Straight forward with accumulate sum            
Set the change of seats for each day.    
If booking = [i, j, k], it needs k more seat on ith to jth day, and we don't need these seats on j+1th day.       
We accumulate these changes then we have the result that we want.        
Complexity      
Time O(booking + N) for one pass on bookings; Space O(N) for the result      

    public int[] corpFlightBookings(int[][] bookings, int n) {
        //prepare for result
        int[] answer = new int[n];
        
        //check for extreme condition
        if(bookings == null || n <= 0){
            return answer;
        }
        
        for(int[] b : bookings){
            answer[b[0] - 1] += b[2]; //往answer[]中加入b[]中对应的座位数
            //check if last flight less than n
            if(b[1] < n){
                answer[b[1]] -= b[2];
            }
        }
        
        for(int i = 1; i < n; ++i){
            answer[i] += answer[i-1];
        }

        return answer;
        
    }



<b> Python </b>      
I. Straight forward     

    def corpFlightBookings(self, bookings, n):
        res = [0] * (n + 1)
        for i, j, k in bookings:
            res[i - 1] += k
            res[j] -= k
        for i in xrange(1, n):
            res[i] += res[i - 1]
        return res[:-1]






### III) 1110. Delete Nodes And Return Forest (medium)      












