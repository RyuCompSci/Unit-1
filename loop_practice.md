# 1.List of squares

```.py
N=int(input())
x=1
y=1
while x**2<=N:
  y=x**2
  print(y)
  x+=1
```

# 2.Least divisor

```.pyN=int(input())
x=1
while N%x!=0 and N>=x+1:
    x+=1
    if N%x==0:
        print(x)
```

# 3.The power of two

```.py
