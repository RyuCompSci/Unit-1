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
N=int(input())
x=0
y=2
if N==1:
    print(0)
    print(1)
else:
    while y<=N:
        y=y*2
        x+=1
    y/=2
    print(x)
    print(y)
```

# 4.Moring jog

```.py
x=int(input())
y=int(input())
z=1
while x<y:
    x*=1.1
    z+=1
print(z)
```

# 5.The length of the sequence

```.py
x=int(input())
y=0
while x!=0:
    x=int(input())
    y+=1
print(y)
```

# 6.THe sum of the sequence

```.py
x=int(input())
y=x
while x!=0:
    x=int(input())
    y+=x
print(y)
```

# 7.
