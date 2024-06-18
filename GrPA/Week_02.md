# Greaded Programming Assignment Week 2

## GrPA 1
<img src="https://github.com/RANJEET1106/PDSA/assets/140232489/9d908414-c9b4-40a1-a40a-a1f2637cd59b" width=650>

## Solution
```py
#python
import string
def combinationSort(strList):
  # Create a dictionary with 26 keys from characters 'a' to 'z', each key has an empty list as value.
  groups = {k: [] for k in string.ascii_lowercase}

  # Using this dictionary to group strings with same initial character.  
  for i in range(len(strList)):
    char=strList[i][0]
    groups[char].append(strList[i])
  
  strList=[]
  # Recreate the list from all the strings in groups, iterating on groups from a to z.
  for char in groups.keys():
    for s in groups[char]:
      strList.append(s)
  
  L1 = strList.copy() # Saving intermediate result to return later.
  i = 1
  left = 0
  # As there can be no more than 100 strings with same initial character.
  # Using insertion sort within group.
  while i<len(strList):
    right = i
    while(right>left and strList[right][0] == strList[right-1][0] and int(strList[right-1][1:])<int(strList[right][1:])):
      strList[right], strList[right-1] = strList[right-1], strList[right]
      right -= 1
    i += 1
  
  return L1, strList
```

## GrPA 2
<img src="https://github.com/RANJEET1106/PDSA/assets/140232489/e41c8efb-cc50-48bd-ad4d-334c71a5a8ae" width=650>

## Solution
```py
#python
def findLargest(L):
  left = 0
  s = len(L)
  right = s-1
  
  # If list has only one element, that is the max.
  if (s==1):
    return L[0]
    
  while (left<=right):
    mid=(left+right)//2
    
    # if mid is at last index, next element to compare will be at index 0
    if (mid == s-1):
      nextToMid = 0
    else:
      nextToMid = mid+1

    if (L[mid] > L[nextToMid]):
      return L[mid]
    elif (L[mid] < L[0]):
      # our element is in left of mid
      right = mid-1
    else:
      # our element is in right of mid
      left = mid+1
```

## GrPA 3

<img src="https://github.com/RANJEET1106/PDSA/assets/140232489/749174df-4868-4cf1-9b37-b9145f63352a" width=650>

## Solution

```py
#python
def mergeInPlace(A, B):
  m = len(A)
  n = len(B)
  if (m < 1 or n < 1):
    return 
  
  # Find the smaller list of A and B.
  for i in range(0, m):
    # A and B are already sorted. B[0] will always be least in B, 
    # as we will maintain its sortedness .
    if (A[i] > B[0]):
      A.swap(i, B, 0)
       
      # move `B[0]` to its correct position in B to maintain the sortedness of B
      j = 0
      while(j < n - 1 and B[j] > B[j + 1]):
        B.swap(j+1, B, j)        
        j += 1
```