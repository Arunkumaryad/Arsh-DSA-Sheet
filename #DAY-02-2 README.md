# DAY 2: Set Matrix Zeroes

## Problem Statements

Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place.


## Example

Example 1:


Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]

Output: [[1,0,1],[0,0,0],[1,0,1]]


Example 2:


Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]

Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
 

 

```C++
#include <bits/stdc++.h>
using namespace std;

 void setZeroes(vector<vector<int>>& matrix) {
        int n = matrix.size();
        int m = matrix[0].size();
        vector<vector<int>> ans = matrix;
        for(int i=0;i<n;i++) {
            for(int j=0;j<m;j++) {
                if(matrix[i][j] == 0) {
                    //for every corresponding row
                    for(int k=0;k<m;k++) {
                        ans[i][k] = 0;
                    }
                }
            }
        }
        for(int i=0;i<n;i++) {
            for(int j=0;j<m;j++) {
                if(matrix[i][j] == 0) {
                    //for every column
                    for(int k=0;k<n;k++) {
                        ans[k][j] = 0;
                    }
                }
            }
        }
        for(int i=0;i<n;i++) {
            for(int j=0;j<m;j++) {
                matrix[i][j] = ans[i][j];
            }
        }
}
int main() {
  int n,m;
  cin>>n>>m;
  vector<vector<int>>matrix(n,vector<int>(m,-1));
  for(int i=0;i<n;i++) {
    for(int j=0;j<m;j++) {
      cin>>matrix[i][j];
    }
  }
  cout<<"Before set matrix zero: "<<endl;
  for(int i=0;i<n;i++) {
    for(int j=0;j<m;j++) {
      cout<<matrix[i][j]<<" ";
    }
  }
  cout<<endl;
  cout<<endl;
  cout<<"Before set matrix zero: "<<endl;
  setZeroes(matrix);
  for(int i=0;i<n;i++) {
    for(int j=0;j<m;j++) {
      cout<<matrix[i][j]<<" ";
    }
  }
  return 0;
}
```
