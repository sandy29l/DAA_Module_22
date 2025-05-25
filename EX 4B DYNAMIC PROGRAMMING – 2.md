# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:01.04.2025
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm:
```
1.Create a 2D table lookup of size (m+1) x (n+1), where m and n are the lengths of strings X and Y, respectively.
2.Initialize maxLength as 0 and endingIndex as m to store the end index of the longest common substring.
3.Loop through each character of both strings (X[i-1] and Y[j-1]):
4.If the characters match, update lookup[i][j] = lookup[i-1][j-1] + 1.
5.If the characters don't match, set lookup[i][j] = 0.
6.Track the maximum length found and update maxLength and endingIndex accordingly.
7.The longest common substring is the substring of X that starts from endingIndex - maxLength and ends at endingIndex.
```
## Program:
```

Program to implement the longest common substring problem
Developed by: SANTHOSH L
Register Number:  212222100046
  
def LCS(X, Y, m, n):
 
    maxLength = 0          
    endingIndex = m        
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]
    
if __name__ == '__main__':
    X = input()
    Y = input()
    m = len(X)
    n = len(Y)
    print('The longest common substring is', LCS(X, Y, m, n))

```

## Output:

![Screenshot 2025-04-30 205220](https://github.com/user-attachments/assets/2fa08b2e-6eb7-4679-907d-cf6803cd75bf)

## Result:
Thus the program was executed successfully for finding the longest common substring .
