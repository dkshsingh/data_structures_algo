# data_structures_algo
## 1. Kadane's Algorithm
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

         
