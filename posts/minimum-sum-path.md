---
title: "Minimum Sum Path in a Matrix using DP"
subtitle: "Exploring Dynamic Programming: Minimum Sum Path in a Matrix"
date: "2023-09-16"
---

# Exploring Dynamic Programming: Minimum Sum Path in a Matrix

## Introduction

In the realm of computer science and algorithms, dynamic programming is a powerful technique used to solve a wide range of problems efficiently. One such problem is finding the minimum sum path in a matrix. In this blog, we'll dissect a C++ code that employs dynamic programming to tackle this challenge. Let's dive into the code and understand how it works.

## Understanding the Code

The code provided is written in C++ and aims to find the minimum sum path in a 2D matrix. Here's a breakdown of the main components:

### Include Statements

```cpp
#include <bits/stdc++.h>
using namespace std;
```
This section includes the necessary standard libraries, allowing us to use functions like vector and cout.

### Helper Function for Minimum Sum Path:

```cpp
int minSumPathUtil(int i, int j, vector<vector<int>> &matrix, vector<vector<int>> &dp) {
```

This function is a recursive helper that calculates the minimum sum path from cell (i, j) to (0, 0) in the matrix. It takes four parameters:

 * i and j: The current row and column indices.
 * matrix: The 2D matrix representing the grid.
 * dp: A memoization table (Dynamic Programming) to store intermediate results.

The function employs recursion to explore the possible paths.

### Base Cases:

```cpp
    if (i == 0 && j == 0)
        return matrix[0][0];
    if (i < 0 || j < 0)
        return INT_MAX;
    if (dp[i][j] != -1)
        return dp[i][j];
```

These are the base cases for the recursive function:

* If we are at the top-left corner, the minimum path sum is the value at (0, 0).
* If we go out of bounds, we return a large value to avoid considering this path.
* If the result for this cell is already computed, it is retrieved from the memoization table.

### Calculating Minimum Sum:

```cpp
    int up = matrix[i][j] + minSumPathUtil(i - 1, j, matrix, dp);
    int left = matrix[i][j] + minSumPathUtil(i, j - 1, matrix, dp);
```

Here, we calculate the minimum sum path by considering two possible moves: moving up and moving left. We add the value of the current cell to the minimum of the results obtained from the recursive calls.

### Storing and Returning Result:

```cpp
    return dp[i][j] = min(up, left);
```

We store the result in the memoization table dp and return the minimum of the two possible paths.

### Main Function:

```cpp
int main() {
    cout << "Minimum sum path: " << minSumPath(n, m, matrix) << endl;
    return 0;
}
```

In the main function, we initialize the matrix, get its dimensions n and m, and then call the minSumPath function to find the minimum sum path. The result is printed to the console.

### Conclusion

This C++ code elegantly demonstrates the application of dynamic programming to find the minimum sum path in a matrix. By breaking down the problem into smaller subproblems and utilizing memoization, it efficiently computes the desired result. Understanding such algorithms and techniques can greatly enhance one's problem-solving skills in the field of computer science.