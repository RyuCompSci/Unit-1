# 1. Minimum of two numbers

![](if_11.jpg)

```.py
a=input("Enter a figure")
b=input("Enter another figure")
if a>b:
    print(b)
else :
    print(a)
```

# 2. Sign function

![](if_12.jpg)

```.py
x=int(input("Enter an integer"))
if x>0:
    print(1)
elif x<0:
    print(-1)
else:
    print(0)
```

# 3. Minimum of three numbers

![](if_13.jpg)

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

# 4. Equal numbers

![](if_14.jpg)

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

# 5. Rook move

![](if_21.jpg)

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
# 6. Chessboard -same color-

![](if_22.jpg)

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

# 7. King move

![](if_23.jpg)

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

# 8. Bishop move

![](if_24.jpg)

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

# 9. Queen move

![](if_25.jpg)

```.py
a=int(input("Enter an integer of 1 digit"))
b=int(input("Enter an integer of 1 digit"))
c=int(input("Enter an integer of 1 digit"))
d=int(input("Enter an integer of 1 digit"))
if abs(b-d)>=1 and abs(a-c)==abs(b-d):
    print("YES")
elif a==c or b==d:
    print("YES")
else:
    print("NO")
```

# 10. Knight move

![](if_31.jpg)

```.py
a=int(input("Enter an integer of 1 digit"))
b=int(input("Enter an integer of 1 digit"))
c=int(input("Enter an integer of 1 digit"))
d=int(input("Enter an integer of 1 digit"))
if abs(a-c)==1 and abs(b-d)==2:
    print("YES")
elif abs(a-c)==2 and abs(b-d)==1:
    print("YES")
else:
    print("NO")
```

# 11. Chocolate bar

![](if_32.jpg)

```.py
n=int(input("Enter an integer"))
m=int(input("Enter an integer"))
k=int(input("Enter an integer"))
if k%m==0 and k/m<=n:
    print("YES")
elif k%n==0 and k/n<=m:
    print("YES")
else:
    print("NO")
```

# 12. leap year

![](if_33.jpg)

```.py
x=int(input("Enter the year you were born in "))
if x%4==0 and x%100>=1:
    print("LEAP")
elif x%400==0:
    print("LEAP")
else:
    print("COMMON")
```
