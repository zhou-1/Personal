## First try in contest.     

### I) Distribute Candies to People (easy)     
We distribute some number of candies, to a row of n = num_people people in the following way:      
We then give 1 candy to the first person, 2 candies to the second person, and so on until we give n candies to the last person.      
Then, we go back to the start of the row, giving n + 1 candies to the first person, n + 2 candies to the second person, and so on until we give 2 * n candies to the last person.      
This process repeats (with us giving one more candy each time, and moving to the start of the row after we reach the end) until we run out of candies.  The last person will receive all of our remaining candies (not necessarily one more than the previous gift).         

Java    

    public int[] distributeCandies(int candies, int num_people) {
        int[] people = new int[num_people];
        for (int give = 0; candies > 0; candies -= give) {
            people[give % num_people] +=  Math.min(candies, ++give);
        }
        return people;
    }

Python    

    def distributeCandies(self, candies, n):
        res = [0] * n
        i = 0
        while candies > 0:
            res[i % n] += min(candies, i + 1)
            candies -= i + 1
            i += 1
        return res


### II) Path In Zigzag Labelled Binary Tree (easy)         
In an infinite binary tree where every node has two children, the nodes are labelled in row order.      
In the odd numbered rows (ie., the first, third, fifth,...), the labelling is left to right, while in the even numbered rows (second, fourth, sixth,...), the labelling is right to left.       
![Explain Image1](img/contest0-II-0.png ) 

Given the label of a node in this tree, return the labels in the path from the root of the tree to the node with that label.       

Example 1:      
Input: label = 14    
Output: [1,3,4,14]     

Example 2:     
Input: label = 26    
Output: [1,2,6,10,26]     

Constraints:     
1 <= label <= 10^6       

Thoughts    
1. Calculate current depth of the label    
2. Calculate offset (for each depth, values lie from 2^d -> 2^(d+1) -1    
3. Find the real parent based on offset   
4. Repeat until we reach 1    

Java     

    public List<Integer> pathInZigZagTree(int label) {
        List<Integer> result = new ArrayList<>();
        int parent = label;
        result.add(0, parent);

        while(parent != 1) {
            int d = (int)(Math.log(parent)/Math.log(2));
            int offset = (int)Math.pow(2, d+1) - 1 - parent;
            parent = ((int)Math.pow(2, d) + offset) / 2;
            result.add(0, parent);   
        }
        
        return result;
    }

Python

    # In the same line, the biggest = smallest * 2 - 1, which leads to the factor 3.
    # And also, each parent is the half of their children, which leads to the pow of 2.

    def pathInZigZagTree(self, x):
        return self.pathInZigZagTree(3 * 2 ** (len(bin(x)) - 4) - 1 - x / 2) + [x] if x > 1 else [1]


### 3) 1105. Filling Bookcase Shelves (medium)      
We have a sequence of books: the i-th book has thickness books[i][0] and height books[i][1].    
We want to place these books in order onto bookcase shelves that have total width shelf_width.      
We choose some of the books to place on this shelf (such that the sum of their thickness is <= shelf_width), then build another level of shelf of the bookcase so that the total height of the bookcase has increased by the maximum height of the books we just put down.  We repeat this process until there are no more books to place.     
Note again that at each step of the above process, the order of the books we place is the same order as the given sequence of books.  For example, if we have an ordered list of 5 books, we might place the first and second book onto the first shelf, the third book on the second shelf, and the fourth and fifth book on the last shelf.       
Return the minimum possible height that the total bookshelf can be after placing shelves in this manner.      

Example 1:      
![Explain Image2](img/contest0-III-0.png )      
Input: books = [[1,1],[2,3],[2,3],[1,1],[1,1],[1,1],[1,2]], shelf_width = 4      
Output: 6   
Explanation:    
The sum of the heights of the 3 shelves are 1 + 3 + 2 = 6.   
Notice that book number 2 does not have to be on the first shelf.       

Constraints:    
1 <= books.length <= 1000     
1 <= books[i][0] <= shelf_width <= 1000     
1 <= books[i][1] <= 1000       

Thoughts    
For each book, we first put it on a new level of the shelf which is the least preferable way to do, in this case the current height will be dp[i - 1] + books[i- 1][1]. Then, we check back previously put books and see if it is possible to get better arrangement(less height) by putting the current book together with the books at previous level of the shelf. If better arrangement is possible, dp[i] will be updated. The inner loop will terminate once accumulated width exceeds the bookshelf's width.        

Java   

    public int minHeightShelves(int[][] books, int shelf_width) {
        //prepare for result
        int res = 0;
        
        int n = books.length; //how many books
        int dp[] = new int[n + 1];
        
        for(int i = 1; i <= n; i++){
            int height = books[i - 1][1];
            int width = books[i - 1][0];
            dp[i] = dp[i - 1] + height;  //add current height first
            for(int j = i - 1; j > 0 && width + books[j-1][0] <= shelf_width; j--){
                height = Math.max(height, books[j-1][1]); //which is higher, current book i -1 or prvious book i-2
                width += books[j-1][0];
                dp[i] = Math.min(dp[i], height + dp[j - 1]);  
                //which is shorter, height of current book + dp[i-1] OR compared height + dp[i - 2].     
                
                /*For me , "dp[i] = Math.min(dp[i], height + dp[j - 1]);" is most difficult part to understand. It is asking us to                         compare "dp[i]: height of current book + dp[i - 1]" WITH "height + dp[j - 1]: height of previous book + dp[i - 2]".
                  i.e. dp[3] in books = [[1,1],[2,3],[2,3],[1,1],[1,1],[1,1],[1,2]], shelf_width = 4.
                  dp[i] = dp[3] = dp[2] + books[2][1] = 3 + 3 = 6;
                  In second for loop: height = max(3, books[1][1] which is 3 also) = 3;
                  so, dp[3] = min(6, 3 + dp[1]) = 4.
                */  
            }   
        }
        
        res = dp[n];
        return res;
    }
    
Python    

    def minHeightShelves(self, books: List[List[int]], shelf_width: int) -> int:
        n = len(books)
        dp = [float('inf') for _ in range(n + 1)]
        dp[0] = 0
        for i in range(1, n + 1):
            max_width = shelf_width
            max_height = 0
            j = i - 1
            while j >= 0 and max_width - books[j][0] >= 0:
                max_width -= books[j][0]
                max_height = max(max_height, books[j][1])
                dp[i] = min(dp[i], dp[j] + max_height)
                j -= 1
        return dp[n]














