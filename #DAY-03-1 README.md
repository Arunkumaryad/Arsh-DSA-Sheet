# DAY 3: Move Zeroes

## Problem Statements

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

 


## Example

Example 1:

Input: nums = [0,1,0,3,12]

Output: [1,3,12,0,0]

Example 2:

Input: nums = [0]

Output: [0]

 

```C++
#include <bits/stdc++.h>
using namespace std;

 void moveZeroes(vector<int>& nums) {
       int n = nums.size();
       int i = 0;
       for(int j=0;j<n;j++) {
        if(nums[j] != 0) {
            swap(nums[i],nums[j]);
            i++;
        }
       }
  }

int main() {
  int n;
  cin>>n;
  vector<int>arr(n);
  for(int i=0;i<n;i++) {
    cin>>arr[i];
  }
  cout<<"Before: " <<endl;
  for(int i=0;i<n;i++) {
    cout<<arr[i]<<" ";
  }
  cout<<endl;
  moveZeroes(arr);
  cout<<"After: " <<endl;
  for(int i=0;i<n;i++) {
    cout<<arr[i]<<" ";
  }
  return 0;
}
```
