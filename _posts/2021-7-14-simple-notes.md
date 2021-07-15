---
layout: post
title: Simple Programming Terminology
subtitle: so I don't forget, I guess
description: Notes, in my own words, of various coding terms
tags: [Notes, Terminology, Pseudo]
readtime: true
---

### Encapsulation

Encapsulation refers to hiding variables within a class, only accessible by methods of the class (getters/setters)

Example: Notice how balance is private. It can only be accessed with the getBalance() method

{% highlight javascript linenos %}

class BankAccount {
  private double balance = 0;
  public void deposit(double x) {
    if(x > 0) {
      balance += x;
    }
  }
  
  public double getBalance() {
    return balance;
  }
}

{% endhighlight %}

Benefits:
- Control of the way data is accessed or modified
- More flexible and easily changed code
- Ability to change one part of the code without affecting other parts
