# DAY 4: Chocolate Distribution Problem


## Problem Statements

Given an array A[ ] of positive integers of size N, where each value represents the number of chocolates in a packet. Each packet can have a variable number of chocolates. There are M students, the task is to distribute chocolate packets among M students such that :
1. Each student gets exactly one packet.
2. The difference between maximum number of chocolates given to a student and minimum number of chocolates given to a student is minimum.
 


## Example

Example 1:

Input:
N = 8, M = 5

A = {3, 4, 1, 9, 56, 7, 9, 12}

Output: 6

Explanation: The minimum difference between maximum chocolates and minimum chocolates is 9 - 3 = 6 by choosing following M packets : {3, 4, 9, 7, 9}.


Example 2:

Input:
N = 7, M = 3

A = {7, 3, 2, 4, 9, 12, 56}

Output: 2

Explanation: The minimum difference between maximum chocolates and minimum chocolates is 4 - 2 = 2 by choosing following M packets : {3, 2, 4}.

 

```C++
#include <bits/stdc++.h>
using namespace std;

long long findMinDiff(vector<long long> a, long long n, long long m) {
    //code
    int i = 0;
    int j = m-1;
    long long ans = INT_MAX;
    sort(a.begin(),a.end());
    while(j < n) {
        long long diff = a[j] - a[i];
        ans = min(ans,diff);
        i++;
        j++;
    }
    return ans;
    
  }  

int main() {
  int n,m;
  cin>>n>>m;
  vector<long long>arr(n);
  for(int i=0;i<n;i++) {
    cin>>arr[i];
  }
  long long ans = findMinDiff(arr,n,m);
  cout<<ans<<endl;
  return 0;
}
```
