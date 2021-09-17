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

# 6.The sum of the sequence

```.py
x=int(input())
y=x
while x!=0:
    x=int(input())
    y+=x
print(y)
```

# 7.The average of the sequence

```.py
x=int(input())
y=x
z=0
while x!=0:
    x=int(input())
    y+=x
    z+=1
y/=z
print(y)
```

# 8.The maximum of the sequence

```.py
x=int(input())
y=x
while x!=0:
    x=int(input())
    y=((x+y)+abs(x-y))//2
print(y)
```

# 9.The index of the maximum of a sequence

```.py
x=int(input())
y=x
z=[x]
while x!=0:
    x=int(input())
    z.append(x)
    y=((x+y)+abs(x-y))//2
a=z.index(y)+1
print(a)
```

# 10.The number of even elements of the sequence

```.py
x=1
y=0
while x!=0:
    x=int(input())
    if x%2==0:
        y+=1
    else:
        y+=0
y-=1
print(y)
```

# 11.The number of elements that are greater than the previous one

```.py
x=1
y=int(input())
z=0
while x!=0:
    x=int(input())
    if x>y:
        z+=1
    else:
        z+=0
    y=x
print(z)
```

# 12.The second maximum

```.py

