# Lists

## Question 1 - Large

```python
N = int(input())

list1 = list()
for i in range(N):
    list1.append(int(input()))

average = 0
for l in list1:
    average += l
average /= N

# average = sum(list1)/len(list1)

for l in list1:
    if l > average:
        print(l, end=' ')
```



## Question 2 - Let's Count

```python
def find_freq(list1):
    freq = [0] * 101
    for l in list1:
        freq[l] += 1
    for i, f in enumerate(freq):
        if f > 0:
            print(str(i) + ' --> ' + str(f))


find_freq([5, 10, 2, 5, 50, 5, 10, 1, 2, 2])
```



## Question 3 - Fifth Powers

```python
list1 = list(map(int, input().split()))
print([x**5 for x in list1])
```
<br /><br /><br />

## Question 4 - To the left

```python
def rotate(l, n):
    return l[n:] + l[:n]


print(rotate([1, 2, 3, 4, 5], 2))
```



## Question 5 - Reverse

```python
N = int(input())

list1 = list()
for i in range(N):
    list1.append(int(input()))

# a
print(list1[::-1])

# b
list1 = list1[::-1]
# list1.reverse()
print(list1)
```


## Question 6 - Remove X

```python
list1 = [5, 20, 15, 20, 25, 50, 20]


def removeValue(sampleList, val):
    return [value for value in sampleList if value != val]


resList = removeValue(list1, 20)
print(resList)
```
<br /><br /><br /><br /><br /><br />
## Question 7 - Remove Duplicates

```python
def remove_duplicates(list1):
    result = []
    for i in list1:
        if i not in result:
            result.append(i)
    return result
    # return list(dict.fromkeys(list1))


example = [1, 1, 1, 1, 1, 2, 2, 2, 3, 2, 2, 4, 5]
print(remove_duplicates(example))

```

## Question 8 - Odd Occurrences

```python
def oddones(l):
    mylist = []

    for i in range(len(l)):
        if not l[i] in mylist:
            mylist.append(l[i])
        else:
            mylist.remove(l[i])

    for i in range(len(mylist)):
        print(mylist[i], end=' ')


oddones([1, 1, 2, 3, 3, 3])
```
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
# Tuples

## Question 9 - Fractions

```python
def simplify(nom, denom):
    factor = min(nom, denom)
    while True:
        if nom % factor == 0 and denom % factor == 0:
            nom //= factor
            denom //= factor
        factor -= 1
        if factor == 1:
            break
    return nom, denom


def addition(frac1, frac2):
    common_denominator = frac1[1] * frac2[1]
    nominator_sum = frac1[0] * frac2[1] + frac2[0] * frac1[1]
    return simplify(nominator_sum, common_denominator)


print(addition((3, 5), (4, 8)))
```

## Question 10 - Points

### Question 10a - Distance

```python
def distance(point1, point2):
    return ((point1[0] - point2[0]) ** 2 + (point1[1] - point2[1]) ** 2) ** (1 / 2)


print(distance((3, 0), (0, 4)))
```

### Question 10b - Closest

```python
def distance(point1, point2):
    return ((point1[0] - point2[0]) ** 2 + (point1[1] - point2[1]) ** 2) ** (1 / 2)


def closest(point1, point2):
    dist1 = distance(point1, (0, 0))
    dist2 = distance(point2, (0, 0))
    return point2 if dist1 > dist2 else point1


print(closest((3, 0), (0, 4)))
```
<br /><br /><br /><br /><br />
### Question 10c - Farthest

```python
def distance(point1, point2):
    return ((point1[0] - point2[0]) ** 2 + (point1[1] - point2[1]) ** 2) ** (1 / 2)


N = int(input())
points = []
for i in range(N):
    x, y = input().split()
    points.append((int(x), int(y)))

max_dist = None
for ix, p in enumerate(points):
    for p2 in points[ix + 1:]:
        dist = distance(p, p2)
        if max_dist is None or dist > max_dist:
            max_dist = dist
            farthest = (p, p2)

print(farthest)
```

