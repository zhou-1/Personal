### I) 1122. Relative Sort Array        
Given two arrays arr1 and arr2, the elements of arr2 are distinct, and all elements in arr2 are also in arr1.      
Sort the elements of arr1 such that the relative ordering of items in arr1 are the same as in arr2.  Elements that don't appear in arr2 should be placed at the end of arr1 in ascending order.     

Example 1:    
Input: arr1 = [2,3,1,3,2,4,6,7,9,2,19], arr2 = [2,1,4,3,9,6]    
Output: [2,2,2,1,4,3,3,9,6,7,19]      

Constraints:    
arr1.length, arr2.length <= 1000   
0 <= arr1[i], arr2[i] <= 1000   
Each arr2[i] is distinct.    
Each arr2[i] is in arr1.      


<b> Difficult part: List<Integer>, Integer[], int[]. </b>             
https://blog.csdn.net/weixin_41615787/article/details/85115620      

Solution:    
My solution. HashMap<element, freq> to record each element and its frequence in arr1. First iterate for each element in arr2, then iterate for remaining elements.     
https://leetcode.com/problems/relative-sort-array/discuss/334576/Java-HashMap-solution       

Custom sorting.    
First, count each number in arr1; then sort the common numbers in both arrays; last sort the numbers only in arr1.     
<b> Java </b>     

    public int[] relativeSortArray(int[] arr1, int[] arr2) {
        int k = 0;
        int[] cnt = new int[1001], ans = new int[arr1.length];
        for (int i : arr1)                      // Count each number in arr1.
            ++cnt[i];
        for (int i : arr2)                      // Sort the common numbers in both arrays.
            while (cnt[i]-- > 0)
                ans[k++] = i;
        for (int i = 0; i < 1001; ++i)          // Sort the numbers only in arr1.
            while (cnt[i]-- > 0)
                ans[k++] = i;
        return ans;
    }


<b> Python </b>      

    def relativeSortArray(self, arr1: List[int], arr2: List[int]) -> List[int]:
        ans, cnt = [], collections.Counter(arr1)         # Count each number in arr1
        for i in arr2:
            if cnt[i]: ans.extend([i] * cnt.pop(i))      # Sort the common numbers in both arrays. 
        for i in range(1001):               
            if cnt[i]: ans.extend([i] * cnt.pop(i))      # Sort the numbers only in arr1.
        return ans



