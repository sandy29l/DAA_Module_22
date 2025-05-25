# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:08.04.2025
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm:
```
1. If the first string is empty, return the length of the second string (insert all characters).
2.If the second string is empty, return the length of the first string (delete all characters).
3.If the last characters of both strings match, move to the next characters by recursively calling the function for substrings excluding the last character.
4.If the last characters don’t match, recursively compute the edit distance considering:
5.Deleting the last character from str1.
6.Inserting the last character into str1.
7.Substituting the last character in str1 with the last character in str2.
8.The minimum of the three operations is chosen, adding 1 to account for the operation itself.  
```
## Program:
```

Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method
Developed by: SANTHOSH L
Register Number:  212222100046


def ed(x,y,m,n):
    if m==0:
        return n
    if n==0:
        return m
    if x[m-1]==y[n-1]:
        return ed(x,y,m-1,n-1)
    return 1+min(ed(x,y,m-1,n-1),ed(x,y,m,n-1),ed(x,y,m-1,n))
    
    
x=input()
y=input()
print("Edit Distance",ed(x,y,len(x),len(y)))
```

## Output:
![Screenshot 2025-04-30 205819](https://github.com/user-attachments/assets/cdfb8dde-98fd-4679-985e-4982574d71cf)

## Result:
Thus the program was executed successfully for finding edit distance between two strings.
