# DAY 1: Find the Duplicate Number

## Problem Statements

Given an array of integers nums containing n + 1 integers where each integer is in the range [1,n] inclusive.

There is only one repeated number in nums, return this repeated number.

You must solve the problem without modifying the array nums and using only constant extra space.

## Example

Example 1:
Input: nums = [1,3,4,2,2]
Output: 2

Example 2:
Input: nums = [3,1,3,4,2]
Output: 3

Example 3:
Input: nums = [3,3,3,3,3]
Output: 3

 

```C++
#include <bits/stdc++.h>
using namespace std;

int findDuplicate(vector<int>& arr) {
  int n = arr.size();
  sort(arr.begin(),arr.end());
  for(int i=0;i<n-1;i++) {
    if(arr[i] == arr[i+1]) {
      return arr[i];
    }
  }
  return 0;
}

int main() {
  int n;
  cin>>n;
  vector<int>arr(n);
  for(int i=0;i<n;i++) {
    cin>>arr[i];
  }
  int ans = findDuplicate(arr);
  cout<<"Duplicate number is: "<<ans<<endl;
  return 0;
}
```

