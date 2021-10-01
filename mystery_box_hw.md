## Mystery Box 1

```.py
def mystery_box1(inputstr,capital):
    rev = ""
    if capital == True:
        inputstr2=inputstr.lower()
        for i in range(len(inputstr2)):
            rev +=inputstr2[len(inputstr2)-i-1]
    else:
        for i in range(len(inputstr)):
            rev +=inputstr[len(inputstr)-i-1]


    return rev


result=mystery_box1("Hello",True)
print(result)
result=mystery_box1("Hello",False)
print(result)
```

## Mystery Box 2

```.py
def mystery_box2(m_ad):
    name=""
    num=0
    while m_ad[num]!="@":
        name += m_ad[num]
        num+=1
    num=0
    first_name=""
    while name[num]!=".":
        first_name += name[num]
        num+=1
    last_name = name.replace(first_name,"")
    last_name = last_name.replace(".","")
    first_name=first_name.capitalize()
    last_name=last_name.capitalize()
    full_name=first_name+" "+last_name
    com=m_ad.replace(name,"")
    com=com.replace("@","")
    return full_name+"\n"+com

result = mystery_box2("john.doe@gmail.com")
print(result)
```

## Mystery Box 3

```.py
def com_mul(input1,input2,input3):
    if input1<input2 and input1<input3:
        smallest=input1
    elif input2<input1 and input2<input1:
        smallest=input2
    elif input3<input2 and input3<input1:
        smallest=input3
    elif input1==input2 and input1<input3:
        smallest=input1
    elif input1==input3 and input1<input2:
        smallest=input1
    elif input3==input2 and input2<input1:
        smallest=input2
    n=2
    cf=[]
    for i in range(smallest):
        if input1%n==input2%n==input3%n==0:
            cf.append(n)
        n+=1
    if len(cf)==0:
        scm=input1*input2*input3
    else:
        lcf=max(cf)
        scm=(input1//lcf)*(input2//lcf)*(input3//lcf)*lcf
    return scm

result = com_mul(8,6,2)
print(result)
result = com_mul(18,4,7)
print(result)
result = com_mul(5,10,7)
print(result)
result = com_mul(5,6,3)
print(result)
```

## Mystery Box 4

```.py
def ibscore(ip1,ip2,ip3,ip4,ip5,ip6,ip7):
    total=ip1+ip2+ip3+ip4+ip5+ip6+ip7
    num=7
    if ip1>7:
        total-=ip1
        num -= 1
    if ip2>7:
        total-=ip2
        num -= 1
    if ip3>7:
        total-=ip3
        num -= 1
    if ip4>7:
        total-=ip4
        num -= 1
    if ip5>7:
        total-=ip5
        num -= 1
    if ip6>7:
        total-=ip6
        num -= 1
    if ip7>7:
        total-=ip7
        num -= 1
    average=total/num
    return average

result = ibscore(5,6,3,8,1,7,9)
print(result)
```
