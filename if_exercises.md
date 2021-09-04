# 1. Minimum of two numbers

```.py
a=input("Enter a figure")
b=input("Enter another figure")
if a>b:
    print(b)
else :
    print(a)
```

# Sign function

```.py
x=int(input("Enter an integer"))
if x>0:
    print(1)
elif x<0:
    print(-1)
else:
    print(0)
```

# Minimum of three numbers

```.py
x=int(input("Enter an integer"))
y=int(input("Enter another integer"))
z=int(input("Enter another integer"))
if x<y and x<z:
    print(x)
elif y<x and y<z:
    print(y)
elif z<x and z<y:
    print(z)
```

# Equal numbers

```.py
x=int(input("Enter an integer"))
y=int(input("Enter another integer"))
z=int(input("Enter another integer"))
if x==y==z:
    print(3)
elif x==y!=z or x==z!=y or y==z!=x:
    print(2)
else:
    print(0)
```

# Rook move

```.py
a=int(input("Enter a figure of 1 digit"))
b=int(input("Enter a figure of 1 digit"))
c=int(input("Enter a figure of 1 digit"))
d=int(input("Enter a figure of 1 digit"))
if a==c or b==d:
    print("YES")
else:
    print("NO")
```
# Chessboard -same color-

```.py
a=int(input("Enter an integer of 1 digit"))
b=int(input("Enter an integer of 1 digit"))
c=int(input("Enter an integer of 1 digit"))
d=int(input("Enter an integer of 1 digit"))
if (a+b+c+d)%2==0:
    print("YES")
else:
    print("NO")
```

# King move

```.py
a=int(input("Enter an integer of 1 digit"))
b=int(input("Enter an integer of 1 digit"))
c=int(input("Enter an integer of 1 digit"))
d=int(input("Enter an integer of 1 digit"))
if -1<=(a-c)<=1 and -1<=(b-d)<=1:
    print("YES")
else:
    print("NO")
```

# Bishop move

```.py
a=int(input("Enter an integer of 1 digit"))
b=int(input("Enter an integer of 1 digit"))
c=int(input("Enter an integer of 1 digit"))
d=int(input("Enter an integer of 1 digit"))
if abs(b-d)>=1 and abs(a-c)==abs(b-d):
    print("YES")
else:
    print("NO")
```

# Queen move
# Knight move
# Chocolate bar
# leap year
