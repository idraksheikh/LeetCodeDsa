[Problem Statement](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118820/offering/1381870)

### Solution using Kadane's Algorithm

```java

import java.util.* ;
import java.io.*; 

public class Solution {
	
	public static long maxSubarraySum(int[] arr, int n) {
		// write your code here
        long maxSum=Long.MIN_VALUE;
        long curSum=0;
        for(int i=0;i<n;i++){
            curSum=Math.max(curSum+arr[i],arr[i]);
            maxSum=Math.max(maxSum,curSum);
            
        }
        if(maxSum<0){
            return 0;
        }
        else{
            return maxSum;
        }
	}

}


```
