# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

## Question A

```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```

## Answer A

Since n in this while loop is actually just one number that we are looping through the time complexity would be O(n). The complexity would be linear.

## Question B

```
b)  sum = 0
    for i in range(n):
      i += 1
      for j in range(i + 1, n):
        j += 1
        for k in range(j + 1, n):
          k += 1
          for l in range(k + 1, 10 + k):
            l += 1
            sum += 1
```

## Answer B

This one would be O(n^4) because it has 4 different for loops.

## Question C

```
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```

## Answer C

This one is O(n) because it is linear.

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.

## Answer Exercise II

Since the idea is to minimize the number of eggs dropped, I would use a binary search to find the floor where eggs start to break.

def doesEggBreakHere(n, f):
bottom = 1
top = n
mid = bottom + (top - bottom) // 2

if mid == f:
return "we found the floor"
elif mid > f:
n = mid
doesEggBreakHere(n, f)
else:
n = mid
doesEggBreakHere(n, f)
