# Greaded Programming Assignment Week 3

## GrPA 1
<img src="https://github.com/RANJEET1106/PDSA/assets/140232489/8e950444-fdd4-4fde-af27-c99d308c1f58" width=650>

## Solution
```py
def insertionsort(L): #use this because it is stable sort
    n = len(L)
    if n < 1:
        return(L)
    for i in range(n):
        j = i
        while(j > 0 and L[j][1] > L[j-1][1]):
            (L[j],L[j-1]) = (L[j-1],L[j])
            j = j-1
    return(L)

def DishPrepareOrder(order_list):
    order_count = {}
    R = []
    for order in order_list:
        if order in order_count:
            order_count[order] += 1
        else:
            order_count[order] = 1
    for ID in sorted(order_count.keys()):
        R.append((ID,order_count[ID]))
    R=insertionsort(R)
    Res = []
    for tup in R:
        Res.append(tup[0])
    return Res
```

## GrPA 2
<img src="https://github.com/RANJEET1106/PDSA/assets/140232489/66974f06-75c7-4b6a-a5bd-f49323bd24e6" width=650>

## Solution
```py
class create_stack:
  def __init__(self):
    self.stack = []
  def push(self,d):
    self.stack += [d]
  def pop(self):
    t = self.stack[-1]
    self.stack = self.stack[:-1]
    return t

def EvaluateExpression(exp):
  opt = ['+','-','*','/','**']
  stk = create_stack()
  L = exp.split(' ')
  for i in L:
    if i not in opt:
      stk.push(i)
    else:
      b = stk.pop()
      a = stk.pop()
      res = eval(a + i + b)
      stk.push(str(res))
  return stk.pop()
```

## GrPA 3
<img src="https://github.com/RANJEET1106/PDSA/assets/140232489/7570f152-df09-4049-9b37-06070514f919" width=650>

## Solution
```py
def reverse(root):
  if (root.isEmpty()):
    return root
  temp = root
  prev = None
  while (temp):
    next, temp.next = temp.next, prev
    prev, temp = temp, next
  return prev
```