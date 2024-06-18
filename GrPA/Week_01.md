# Greaded Programming Assignment Week 1

## GrPA -1
<img src=https://github.com/RANJEET1106/PDSA/assets/140232489/90841815-cef7-4a30-9b72-0b66dd2bd9a2 width=650/>

## Solution 

```py
def find_Min_Difference(L,P):
  L.sort()
  N = P
  M = len(L)
  min_diff = max(L) - min(L)
  for i in range(M-N+1):
    if L[i+N-1] - L[i] < min_diff:
      min_diff = L[i+N-1] - L[i]
  return min_diff
```

## GrPA 2
<img width=650 src="https://github.com/RANJEET1106/PDSA/assets/140232489/42803dc8-1edd-410e-b209-a7ed094f1557">

## Solution
```py
def prime(n):
  if n < 2:
    return False
  for i in range(2,n//2+1):
    if n%i==0:
      return False
  return True

def Goldbach(n):
  Res=[]
  for i in range((n//2)+1):
    if prime(i)==True:
      if prime(n-i)==True:
        Res.append((i,n-i))
  return(Res)
```

## GrPA 3
<img width=650 src="https://github.com/RANJEET1106/PDSA/assets/140232489/cbd7fbde-9614-4d37-93c5-761fed0431a1">

## Solution
```py
def odd_one(L):
  P = {}
  for elem in L:
    if type(elem) not in P:
      P[type(elem)] = 0
    P[type(elem)] += 1
  for key, value in P.items():
    if value == 1:
      return key.__name__
```