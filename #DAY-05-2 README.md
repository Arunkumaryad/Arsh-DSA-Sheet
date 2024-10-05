# DAY 5: Subarray Sums Divisible by K


## Problem Statements

Given an integer array nums and an integer k, return the number of non-empty subarrays that have a sum divisible by k.

A subarray is a contiguous part of an array.
 


## Example

Example 1:

Input: nums = [4,5,0,-2,-3,1], k = 5

Output: 7

Explanation: There are 7 subarrays with a sum divisible by k = 5:

[4, 5, 0, -2, -3, 1], [5], [5, 0], [5, 0, -2, -3], [0], [0, -2, -3], [-2, -3]


Example 2:

Input: nums = [5], k = 9

Output: 0
 

```C++
#include <bits/stdc++.h>
using namespace std;

 int subarraysDivByK(vector<int>& nums, int k) {
        int n = nums.size();
        vector<int> sums(k, 0);
        sums[0]++;
        int cnt = 0;
        int currSum = 0;
        for(int i = 0; i<n; i++) {
            currSum = (currSum + nums[i]%k + k)%k;
            cnt += sums[currSum];
            sums[currSum]++;
        }
        return cnt;
  }

int main() {
  int n,k;
  cin>>n>>k;
  vector<int>arr(n);
  for(int i=0;i<n;i++) {
    cin>>arr[i];
  }
  int ans = subarraysDivByK(arr,k);
  cout<<ans<<endl;
  return 0;
}
```

