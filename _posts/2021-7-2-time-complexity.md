---
layout: post
title: Time Complexity
subtitle: Time Complexity & Big O Notation 
description: Notes, in my own words, of using Big O Notation to measure algorithms
tags: [Notes, Time Complexity, Pseudo]
readtime: true
---

*Note: This isn't neccesarily for teaching, but for my own use.*

To Add: "Master Method"

<img src="/img/image-here.png"/>

## What is Time Complexity?

Time Complexity (running time) is a way of measuring how long an algorithm takes to run, and does so accurately despite the system used to test the code (ie, slow vs fast computer). It does not measure in a unit of time, such as seconds, but rather as a function of the input and describes the worse-case scenario.

Take the following code, which returns the smallest value in an array (no specific langauge):

{% highlight javascript linenos %}
function getMinValue(nums) {
  let min
  if (nums.length > 0):
    min = numbers[0]

  for x in nums:
    if (x < min):
      min = x
      
  return min
}
{% endhighlight %}

We can count the number of operations to determine it's time complexity:

- Lines 2-4 use 1 operation each **total: 3**

- Line 6 uses nums.length operations. This depends on the length of the array passed **total: n**

- 7-8 use 1 operation each, but because they are in the loop they happen n times. **total: 2**
  
So because we have a loop with 2 operations, and 3 operations outside the loop, we can say the time complexity of this method is 2(n) + 3

However, that is too specific.

We need to use *Asymptotic analysis* to simplify this, which is a way of describing limiting behavior.

| Equation | n | Output |
| :------ |:--- | :--- |
| 2(n) + 3 | 10 | 23 |
| 2(n) + 3 | 100 | 203 |
| 2(n) + 3 | 1000 | 2003 |
| 2(n) + 3 | 10000 | 20003 |

You can see the +3 really doesn't make a difference as n approaches infinity. As n grows, the constant is less significant. The 2 also has little significance as we approach infinity, so according to asymptotics we simplify **2(n) + 3** to **n**

Therefore we conclude that the time complexity of the getMinValue() method is **O(n)** (We use Big O Notation to describe time complexity.)

Lets take a more complex method:

{% highlight javascript linenos %}
function checkDuplicates(nums) {
  
  let output = false
  
  for (i = 0; i < nums.length; i++) {
    for (j = 0; j < nums.length; j++) {
    
      if(i == j):
        continue

      if(n[i] == n[j]):
        output = true
      
    }
  }
  
  return output
}
{% endhighlight %}

There are 2 nested for loops here, which each run n times. Within these loops are about 2 operations (I supposed the continue and return true don't really count)

Theres also line 3, which counts as 1 operation

So we can give this method a time complexity of O(2n^2 + 1)

However we wanna describe this as it approaches infinity, so we can remove the +1 and the coefficent of 2 to get a time complexity of **O(n^2)**, which is much slower than a time complexity of **O(n)**

A method with 3 nested loops would have a time complexity of **O(n^3)**

## Other time complexities
### (https://dakota-byte.github.io/othersources/) 1 and 2

**O(1)** describes algorithms that take the same amount of time to compute regardless of the input size.

**O(n)** Linear time complexity means that the algorithms take proportionally longer to complete as the input grows. These algorithms imply that the program visits every element from the input.

**O(n^c)** Polynomial running, when c > 1. 2 nested loops will have c = 2 (quadratic), and 3 will have c = 3 (cubed), and so on.

**O(log n)** Logarithmic time complexities usually apply to algorithms that divide problems in half every time.

**O(n log n)** Linearithmic time complexity is slightly slower than a linear algorithm. However, it’s still much better than a polynomial algorithm.

**O(2^n)** Exponential running time means that the calculations performed by an algorithm double every time as the input grows.

**O(n!)** Factorial runtime are terrible, just terrible. (ex. Permutations of a string)


