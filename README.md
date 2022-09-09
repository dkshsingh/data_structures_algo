# data_structures_algo(in Python)
## 1. Kadane's Algorithm(Python Code)
## * Maximum Subarray Sum
         Input : 9(size of array)
           Arr  1 2 7 -4 3 2 -10 9 1
         Output: 11
### code:
        from os import *
        from sys import *
        from collections import *
        from math import *

        from sys import stdin,setrecursionlimit
        setrecursionlimit(10**7)

        def maxSubarraySum(arr, n) :
        cur_sum = 0
        maxsum = 0
        for i in range(n):
            cur_sum = cur_sum + arr[i]
            maxsum = max(maxsum,cur_sum)
            if cur_sum < 0:
                cur_sum = 0
            if maxsum < 0:
                return 0
            else:
                return maxsum
## 2. Dutch national flag algorithm
## * Sort 0 1 2
      Input : 6(size of array)
      Arr:   0 1 2 2 1 0
      Output : 0 0 1 1 2 2  
### code:
       from os import *
       from sys import *
       from collections import *
       from math import *

       from sys import stdin,setrecursionlimit
       setrecursionlimit(10**7)

       def sort012(arr, n) :
       low = 0
       high = n-1
       mid = 0
       while mid <= high:
           if arr[mid] == 0:
               arr[low],arr[mid]=arr[mid],arr[low]
               low=low+1
               mid=mid+1
           elif arr[mid] == 1:
               mid=mid+1
           elif arr[mid] == 2:
               arr[mid],arr[high]=arr[high],arr[mid]
               high=high-1
           else:
               return arr














