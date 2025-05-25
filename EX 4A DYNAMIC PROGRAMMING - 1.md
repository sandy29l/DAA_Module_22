# EX 4A DYNAMIC PROGRAMMING - 1
## DATE: 29.03.2025
## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm:
```
1.Create a 2D table dp where dp[i][j] will store the length of the LCS of the first i characters of string X and the first j characters of string Y. 
2.Initialize the first row and first column with 0.
3.Traverse the strings X and Y:
   If X[i-1] == Y[j-1], then dp[i][j] = dp[i-1][j-1] + 1 (i.e., extend the subsequence by 1).
   Otherwise, dp[i][j] = max(dp[i-1][j], dp[i][j-1]) (i.e., take the longer subsequence without including the current character of X or Y).
4.After filling the table, backtrack from dp[m][n] to construct the LCS string by comparing characters and moving diagonally when they match.
5.The result is stored in the last cell of the table, dp[m][n], representing the length of the LCS.
 ```
## Program:
```

Program to implement the longest common subsequence using Dynamic Programming
Developed by: SANTHOSH L
Register Number:  212222100046


def longest_common_subsequence(X, Y):
    m = len(X)
    n = len(Y)

    dp = [[0] * (n + 1) for _ in range(m + 1)]

    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

    lcs_length = dp[m][n]
    lcs = [''] * lcs_length
    i, j = m, n

    while i > 0 and j > 0:
        if X[i - 1] == Y[j - 1]:
            lcs[lcs_length - 1] = X[i - 1]
            i -= 1
            j -= 1
            lcs_length -= 1
        elif dp[i - 1][j] > dp[i][j - 1]:
            i -= 1
        else:
            j -= 1

    return ''.join(lcs)
X = input()
Y = input()

result = longest_common_subsequence(X, Y)
print(result)

```

## Output:
![Screenshot 2025-04-30 204712](https://github.com/user-attachments/assets/717d1f49-5dd0-4988-a877-84809254c176)

## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
