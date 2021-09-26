## Programming Task 2

Strange Numbers: Given a number as a String N. Multiply all of its digits, and repeat the same with the product obtained till the product consists of only one digit.
Output the number of steps taken to do so.

```.py
x=str(input())
y=len(x)
z=0
a=1
for i in range (y):
    a*=int(x[z])
    z+=1
y=len(str(a))
b=0
while a>=10:
    x = str(a)
    for i in range(y):
        a *= int(x[b])
        b += 1
b+=1
print(b)
```
