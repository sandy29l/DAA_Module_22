# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:05.04.2025
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.

## Algorithm:
```
1.Create a 2D table dp where dp[i][j] represents the length of the longest palindromic subsequence in the substring X[i...j].
2.Set dp[i][i] = 1 for all i because each individual character is a palindrome of length 1.
3.For substrings of length 2 to n:
4.If X[i] == X[j], then dp[i][j] = dp[i+1][j-1] + 2 (i.e., we can extend the palindrome by including both X[i] and X[j]).
5.Otherwise, dp[i][j] = max(dp[i+1][j], dp[i][j-1]) (i.e., we take the maximum length by ignoring one of the characters).
6. The length of the longest palindromic subsequence for the entire string is stored in dp[0][n-1].
```

## Program:
```

Program to implement to find the length of the longest palindromic subsequence in it
Developed by: SANTHOSH L
Register Number:  212222100046

def Lps(X):
    n=len(X)
    dp=[[0 for _ in range(n)] for _ in range(n)]
    
    for x in range(n):
        dp[x][x]=1
        
    for l in range(2,n+1):
        for i in range(n-l+1):
            j=i+l-1
            if X[i]==X[j]:
                dp[i][j]=dp[i+1][j-1]+2
            else:
                dp[i][j]=max(dp[i+1][j],dp[i][j-1])
    return dp[0][n-1]
    
X=input()
print("The length of the LPS is",Lps(X))
        

```

## Output:

![Screenshot 2025-04-30 205608](https://github.com/user-attachments/assets/eaa89930-6956-456e-a912-724cef55adf5)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
