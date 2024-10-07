# DAY 6: Container With Most Water


## Problem Statements

You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.


## Example

Example 1:

Input: height = [1,8,6,2,5,4,8,3,7]

Output: 49

Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.


Example 2:

Input: height = [1,1]

Output: 1


Example 2:

Input: height = [1,1]

Output: 1


```C++
#include <bits/stdc++.h>
using namespace std;

int maxArea(vector<int>& height) {
        int n = height.size();
        int start = 0;
        int end = n-1;
        int ans = 0;
        while(start < end) {
            int diff = min(height[start],height[end]) * (end-start);
            ans = max(ans,diff);
            if(height[start] < height[end]) {
                start++;
            }
            else {
                end--;
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
  int ans = maxArea(arr);
  cout<<ans<<endl;
  return 0;
}
```
