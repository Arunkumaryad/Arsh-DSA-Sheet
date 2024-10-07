# DAY 6: Find All Duplicates in an Array


## Problem Statements

Given an integer array nums of length n where all the integers of nums are in the range [1, n] and each integer appears once or twice, return an array of all the integers that appears twice.

You must write an algorithm that runs in O(n) time and uses only constant auxiliary space, excluding the space needed to store the output.


## Example

Example 1:

Input: nums = [4,3,2,7,8,2,3,1]

Output: [2,3]


Example 2:

Input: nums = [1,1,2]

Output: [1]


Example 3:

Input: nums = [1]

Output: []


```C++
#include <bits/stdc++.h>
using namespace std;

vector<int> findDuplicates(vector<int>& nums) {
        int n = nums.size();
        vector<int>ans;
        unordered_map<int,int>mp;
        for(int i=0;i<n;i++) {
            mp[nums[i]]++;
        }
        for(auto it : mp) {
            if(it.second == 2) {
                ans.push_back(it.first);
            }
        }
        return ans;
  }

int main() {
  int n;
  cin>>n;
  vector<int>arr(n);
  for(int i=0;i<n;i++) {
    cin>>arr[i];
  }
  vector<int>ans = findDuplicates(arr);
  for(int i=0;i<ans.size();i++) {
    cout<<ans[i]<<", ";
  }
  return 0;
}
```
