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
I. Straight forward       

    public int[] corpFlightBookings(int[][] bookings, int n) {
        int[]res=new int[n];
        for (int i=0;i<bookings.length;i++){
            for (int j=bookings[i][0]-1;j<=bookings[i][1]-1;j++){
                res[j]=res[j]+bookings[i][2];
            }
        }
        return res;
    }


II. accumulate sum             
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
I. accumulate sum           

    def corpFlightBookings(self, bookings, n):
        res = [0] * (n + 1)
        for i, j, k in bookings:
            res[i - 1] += k
            res[j] -= k
        for i in xrange(1, n):
            res[i] += res[i - 1]
        return res[:-1]






### III) 1110. Delete Nodes And Return Forest (medium)      
Given the root of a binary tree, each node in the tree has a distinct value.      
After deleting all nodes with a value in to_delete, we are left with a forest (a disjoint union of trees).      
Return the roots of the trees in the remaining forest.  You may return the result in any order.        

Example 1:     
![Explain Image1](img/contest1-II-0.png )     
Input: root = [1,2,3,4,5,6,7], to_delete = [3,5]      
Output: [[1,2,null,4],[6],[7]]      
 

Constraints:    
The number of nodes in the given tree is at most 1000.    
Each node has a distinct value between 1 and 1000.     
to_delete.length <= 1000    
to_delete contains distinct values between 1 and 1000.      


Solution:       
<b> Updated!!!! </b>         
1. Why we only need to add the root node of every tree? I mean, for example, "[1,2,null,4]" in "[[1,2,null,4],[6],[7]]", if we only add root node, it will be [[1],[6],[7], right?       
"[1, 2, null, 4]" is simply a way to represent/express a tree structure, since we can't use plain text to actually draw a tree. This way of the representation is "accidentally" same as the way that we usually use to represent an array, but logically it is not an array. Logically it is representing a tree.     
Apart from text, there are many other ways to represent a tree. For example, using the root node of the tree to represent the tree.    
So the return value of delNodes is an array of trees. Each tree is represented by the root node of the tree.      
In the output "[[1,2,null,4],[6],[7]]", the outer brackets represent an array, while the inner brackets represent trees.        

2. What does "return deleted ? null : node;" use for? Is it using for value of node.left / node.right?          
The return value is used by the .left and .right of the upper level of recursion.      

https://leetcode.com/problems/delete-nodes-and-return-forest/discuss/328853/JavaPython-Recursion-Solution      

##### Solve tree problem with recursion first.     
Explanation      
If a node is root (has no parent) and isn't deleted, when will we add it to the result.       

<b> Java </b>      


    class Solution {
    
      Set<Integer> to_delete_set;
      List<TreeNode> res;
    
      public List<TreeNode> delNodes(TreeNode root, int[] to_delete) {
        res = new ArrayList<> ();
        to_delete_set = new HashSet<> ();
        
        //put element in to_delete in to_delete_set
        for(int i: to_delete){
            to_delete_set.add(i);
        }
        
        helper(root, true);
        return res;
        
      }
    
    
      public TreeNode helper(TreeNode node, boolean is_root){
        if(node == null){
            return null;
        }
        //check whether set contains this node or not
        boolean deleted = to_delete_set.contains(node.val);
        
        //if it is root and it doesn't delete
        if(is_root && !deleted){
            res.add(node);
        }
        
        node.left = helper(node.left, deleted);
        node.right = helper(node.right, deleted);
        
        return deleted ? null : node;
      }
 
    }


<b> Python </b>     

    def delNodes(self, root, to_delete):
        to_delete_set = set(to_delete)
        res = []

        def helper(root, is_root):
            if not root: return None
            root_deleted = root.val in to_delete_set
            if is_root and not root_deleted:
                res.append(root)
            root.left = helper(root.left, root_deleted)
            root.right = helper(root.right, root_deleted)
            return None if root_deleted else root
        helper(root, True)
        return res






### IV) 1111. Maximum Nesting Depth of Two Valid Parentheses Strings (medium)             
A string is a valid parentheses string (denoted VPS) if and only if it consists of "(" and ")" characters only, and:      
1.It is the empty string, or       
2.It can be written as AB (A concatenated with B), where A and B are VPS's, or    
3.It can be written as (A), where A is a VPS.      

We can similarly define the nesting depth depth(S) of any VPS S as follows:       
1.depth("") = 0      
2.depth(A + B) = max(depth(A), depth(B)), where A and B are VPS's      
3.depth("(" + A + ")") = 1 + depth(A), where A is a VPS.       

For example,  "", "()()", and "()(()())" are VPS's (with nesting depths 0, 1, and 2), and ")(" and "(()" are not VPS's.      
Given a VPS seq, split it into two disjoint subsequences A and B, such that A and B are VPS's (and A.length + B.length = seq.length).     
Now choose any such A and B such that max(depth(A), depth(B)) is the minimum possible value.       
Return an answer array (of length seq.length) that encodes such a choice of A and B:  answer[i] = 0 if seq[i] is part of A, else answer[i] = 1.  Note that even though multiple answers may exist, you may return any of them.      

Example 1:   
Input: seq = "(()())"      
Output: [0,1,1,1,1,0]     

Example 2:       
Input: seq = "()(())()"    
Output: [0,0,0,1,1,0,1,1]     

Constraints:     
1 <= seq.size <= 10000      


Solution:     


















