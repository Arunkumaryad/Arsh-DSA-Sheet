# DAY 1: Sort Colors

## Problem Statements

Given an array nums with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers 0, 1, and 2 to represent the color red, white, and blue, respectively.

You must solve this problem without using the library's sort function.

## Example

Example 1:

Input: nums = [2,0,2,1,1,0]

Output: [0,0,1,1,2,2]

Example 2:

Input: nums = [2,0,1]

Output: [0,1,2]

 

```C++
#include <bits/stdc++.h>
using namespace std;

 void sortColors(vector<int>& nums) {
        int n = nums.size();
        int zero = 0;
        int one  = 0;
        int two = 0;
        for(int i=0;i<n;i++) {
            if(nums[i] == 0) {
                zero++;
            }
            else if(nums[i] == 1) {
                one++;
            }
            else {
                two++;
            }
        }
        int i = 0;
        while(zero) {
            nums[i] = 0;
            zero--;
            i++;
        }
        while(one) {
            nums[i] = 1;
            one--;
            i++;
        }
        while(two) {
            nums[i] = 2;
            two--;
            i++;
        }
  }

int main() {
  int n;
  cin>>n;
  vector<int>arr(n);
  for(int i=0;i<n;i++) {
    cin>>arr[i];
  }
  cout<<"Before Sorting: " <<endl;
  for(int i=0;i<n;i++) {
    cout<<arr[i]<<" ";
  }
  cout<<endl;
  sortColors(arr);
  cout<<"After Sorting: " <<endl;
  for(int i=0;i<n;i++) {
    cout<<arr[i]<<" ";
  }
  return 0;
}
```
