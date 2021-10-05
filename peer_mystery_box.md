## Paolo's Os

```.py
def paolosos(inputword):
    length=len(inputword)
    num=0
    for i in range(length):
        if inputword[i]=="o":
            num+=1
        else:
            num+=0
    return num
result=paolosos("olo")
print(result)
```

![](
