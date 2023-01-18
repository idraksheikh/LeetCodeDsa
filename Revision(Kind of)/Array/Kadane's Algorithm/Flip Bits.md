### [Problem Statement](https://www.codingninjas.com/codestudio/guided-paths/data-structures-algorithms/content/118820/offering/1381872)

### Brute Force (Kind of)

```java

        int maxSum,curSum,mleft,mright,l;
        maxSum=curSum=mleft=mright=l=0;
        for(int i=0;i<n;i++){
            if(arr[i]==0){
                curSum+=1;
            }
            else{
                curSum-=1;
            }
            if(maxSum<curSum){
                maxSum=curSum;
                mleft=l;
                mright=i;
            }
            if(curSum<0){
                curSum=0;
                l=i+1;
            }
        }
        if(maxSum>0){
            for(int i=mleft;i<=mright;i++){
            if(arr[i]==0){
                arr[i]=1;
            }
            else{
                arr[i]=0;
            }
            }    
        }
        
        int oneCount=0;
        for(int i=0;i<n;i++){
            if(arr[i]==1)oneCount++;
        }
        return oneCount;


```

### More Optimal

```java

int maxSum,curSum,oneCount;
        maxSum=curSum=oneCount=0;
        for(int i=0;i<n;i++){
            curSum+=arr[i]==0?1:-1;
            maxSum=Math.max(maxSum,curSum);
            if(curSum<0)curSum=0;
            if(arr[i]==1)oneCount++;
        }
        return maxSum+oneCount;

```
