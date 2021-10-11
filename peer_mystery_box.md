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


### Berill's
```.py
def repeated_letter(word1, word2):
    num_word1 = 0
    num_word2 = 0
    for i in range(len(word1)):
        word1c = word1.count(word1[i])
        if word1c >= 2:
            num_word1 += 1
        else:
            num_word1 += 0
    for i in range(len(word2)):
        word2c = word2.count(word2[i])
        if word2c >= 2:
            num_word2 += 1
        else:
            num_word2 += 0
    if num_word1 > num_word2:
        output = word1
    elif num_word2 > num_word1:
        output = word2
    elif num_word1 == num_word2:
        output = "None"
    return output

result = repeated_letter("hello", "appreciate")
print(result)
```

### Esslam's

```.py
def unique_letter(word):
    num_word = 0
    for i in range(len(word)):
        wordc = word.count(word[i])
        if wordc >= 2:
            num_word += 1
        else:
            num_word += 0
    if num_word > 0:
        output = False
    else:
        output = True
    return output

result = unique_letter("hello")
print(result)
result = unique_letter("wolf")
print(result)
result = unique_letter("street")
print(result)
```
