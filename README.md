# data_structures_algo_problems(in Python)
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
## 3. Searching and sorting
## * binary search(c++)
      Input:                                                Input:
      N = 5                                                 N=5
      arr[] = {1 2 3 4 5}                                   arr[] = {11 22 33 44 55} 
      K = 4                                                 k = 445
      Output: 3                                             output: -1
      Explanation: 4 appears at index 3.                    Explanation: 445 is not present.

### code:
         class Solution {
         public:
             int binarysearch(int arr[], int n, int k) {
             // code here
                 int l=0,h=n-1;
                 while(l<=h){
                     int mid=l+(h-l)/2;
                     if(arr[mid]==k)
                     return mid;
                     if(arr[mid]<k)
                     l=mid+1;
                     if(arr[mid]>k)
                     h=mid-1;
                    }
                return -1;
                }
             };




## * Search In Rotated Sorted Array(Binary Search)
      Input: 4
      Arr: 2 5 -3 0
      Output: 1
              -1
### code:
    def search(arr, target) :
    low = 0
    high = len(arr)-1
    
    while low <= high:
        mid = (low+high)//2
        if target == arr[mid]:
            return mid
        if arr[low] <= arr[mid]:
            if target > arr[mid] or target < arr[low]:
                low = mid+1
            else:
                high = mid-1
        else:
            if target < arr[mid] or target > arr[high]:
                high = mid-1
            else:
                low = mid+1
    return -1            
    pass

## * Find First and Last Position of Element in Sorted Array
      Input: nums = [5,7,7,8,8,10], target = 8
      Output: [3,4]

      Input: nums = [5,7,7,8,8,10], target = 6
      Output: [-1,-1]

### code:
          class Solution:
         def searchRange(self, nums: List[int], target: int) -> List[int]:
             def search(x):
                 lo, hi = 0, len(nums)           
                 while lo < hi:
                     mid = (lo + hi) // 2
                     if nums[mid] < x:
                         lo = mid+1
                     else:
                         hi = mid                    
                return lo
        
            lo = search(target)
            hi = search(target+1)-1
        
            if lo <= hi:
                return [lo, hi]
                
        return [-1, -1]
## 4. String
## * Convert string
      Input: 3  (test cases)
             I love programming
             they are playing cricket
             good to see you
     Output: I Love Programming
             They Are Playing Cricket
             Good To See You
### code:  
           def convertString(str):
               Ist = [word[0].upper()+word[1:] for word in str.split()]
               str = " ".join(Ist)
           return str
           pass
## * Encode the message
      Input: 3
             aabbc
             abcd
             abbdcaas
      Output: a2b2c1
              a1b1c1d1
              a1b2d1c1a2s1
### code:
          def encode(message):
              result=""
              num = len(message)
              i=0 
              while i <num :
                  k = 1  
                  while (i <num-1 and message[i]== message[i+1]) :
                      k+= 1
                      i+=1 
                   result += ((message[i])+str(k))  #,end=""
                   i+=1
              return result  
              pass


