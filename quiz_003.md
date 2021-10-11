### Given an integer N, show 100 integers with the repeating pattern 0 to N-1, 0 to N-1,... plus addtion of the number

```.py
def rangePatternN(inp):
s=0
for i in range(inp):
  s+=i
d=100//inp
r=100%inp
rr=0
for i in range(r):
  rr+=i
t=s*d+rr
return t
```
