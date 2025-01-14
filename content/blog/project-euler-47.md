---
title: Hello Project-Euler 47, I'm ravish0007
---

Hello again, let us talk to project-euler 47 (https://projecteuler.net/problem=47).
My friend Vin\* is little cool, she bugged me with project-euler-47,
this post is just a text version of my thoughts and few little random walks.

<!--more-->

## Distinct prime factors

```
The first two consecutive numbers to have two distinct prime factors are:

  14 = 2 × 7
  15 = 3 × 5

The first three consecutive numbers to have three distinct prime factors are:

  644 = 2² × 7 × 23
  645 = 3 × 5 × 43
  646 = 2 × 17 × 19.

Find the first four consecutive integers to have four distinct prime factors each. What is the first of these numbers?
```

## Scaffolding main.py

```python
def some_functionality(number):
    pass

import itertools
for number in itertools.count():
    if some_functionality(number):
        print(number)
        break

```

## Re-Read the problem, addressing the previous implementation

```python
def four_consecutive_number_generator(start=0):
    local_number = start
    while True:
        yield [local_number, local_number + 1,
               local_number + 2, local_number + 3]
        local_number += 1

for first_number, second_number, third_number, fourth_number in four_consecutive_number_generator():
    print(first_number, second_number, third_number, fourth_number)
```

## Addressing the structure, and defining functionality

```python
def has_distinct_prime_factors(numbers):
    return true

for numbers in four_consecutive_number_generator():
    if has_distinct_prime_factors(numbers):
        print(numbers)
        break
```

## Defining functionality, a little

```python
def get_factors(number):
    return []

def has_distinct_prime_factors(numbers):
    for each_number in numbers:
        factors = get_factors(each_number)
```

## Putting prime_factors functionality, Hello problem-3

```python
def get_prime_factors(number):
    prime_factors = []

    while number % 2 == 0:
        number = number / 2
        prime_factors.append(2)

    for index in range(3, int(math.sqrt(number)) + 1, 2):
        while n % index == 0:
            prime_factors.append(index)
            number = number / index

    if number > 2:
        prime_factors.append(number)

    return prime_factors

def has_distinct_prime_factors(numbers):
    for each_number in numbers:
        factors = get_prime_factors(each_number)
        print(factors)
```

# All together, and little debugging here and there

```python
import math

def four_consecutive_number_generator(start=0):
    local_number = start
    while True:
        yield [local_number, local_number + 1,
               local_number + 2, local_number + 3]
        local_number += 1

# Hello problem-3, doesn't work for 0, 1
def get_prime_factors(number):
    prime_factors = []

    while number % 2 == 0:
        number = number / 2
        prime_factors.append(2)

    for index in range(3, int(math.sqrt(number)) + 1, 2):
        while number % index == 0:
            prime_factors.append(index)
            number = number / index

    if number > 2:
        prime_factors.append(number)

    return prime_factors

def has_distinct_prime_factors(numbers, length):
    for each_number in numbers:
        factors = get_prime_factors(each_number)
        if len(set(factors)) != length:  # distinct, final piece
            return False
    return True


for numbers in four_consecutive_number_generator(start=1):
    print('processing: ', *numbers, flush=True)
    if has_distinct_prime_factors(numbers, length=4):
        print(numbers)
        break
```

Thank you Euler, Project Euler and Viny.

P.S: https://github.com/ravish0007/projecteuler/blob/main/problem-47/main.py
