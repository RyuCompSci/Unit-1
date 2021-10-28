### Write a function that receives an integer N, and returns all its factores.
### [HL] show also the addition of the factores show if the result is the same as N

```.py
def perfectN(inp):
    sum = 0
    x = 1
    y = []
    for i in range(inp-1):
        if inp%x == 0:
            y.append(x)
            sum += x
        x += 1
    if sum == inp:
        print("TRUE")
    else:
        print("FALSE")
    return y, sum
answer = perfectN(6)
print(answer)
```
