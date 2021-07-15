---
layout: post
title: Simple Programming Terminology
subtitle: Using Java as an example
description: Notes, in my own words, of various coding terms
tags: [Notes, Terminology, Java]
readtime: true
---

Credit: https://www.sololearn.com/learning/1068 (The Sololearn Java Course)

{% highlight javascript linenos %}

{% endhighlight %}

### Encapsulation

Encapsulation refers to hiding variables within a class, only accessible by methods of the class (getters/setters)

Example: Notice how balance is private. It can only be accessed with the getBalance() method

{% highlight javascript linenos %}
// by sololearn 
class BankAccount {
  private double balance = 0;
  public void withdraw(double x) {
    if(balance >= x) {
      balance -= x;
    }
  }
  
  public double getBalance() {
    return balance;
  }
}
{% endhighlight %}

Benefits:
- Better control the way class data is accessed or modified
- Ability to change one part of the code without affecting other parts

### Inheritance

Inheritance refers to one class gaining the properites of another (variables & methods) 

{% highlight javascript linenos %}
// by sololearn
class Animal {
  protected int legs;
  public void eat() {
    System.out.println("Animal eats");
  }
}

class Dog extends Animal {
  Dog() {
    legs = 4;
  }
}
{% endhighlight %}

Above you can see how the Dog subclass has the legs attribute because it extends the Animal superclass.

Note: The "protected" keywords makes legs ONLY visible to the subclasses

Note 2: Constructors are not inherited, but they are called. For example, creating a Dog class would call the constructor of Animal

### Polymorphism

Polymorphism refers to a superclass having multiple subclasses with unique method implementations.

{% highlight javascript linenos %}
// by sololearn
class Animal {
  public void makeSound() {
    System.out.println("Grr...");
  }
}
class Cat extends Animal {
  public void makeSound() {
    System.out.println("Meow");
  }
}
class Dog extends Animal {
  public void makeSound() {
    System.out.println("Woof");
  }
}
{% endhighlight %}

Here, Cat and Dog extend the Animal class, and each have their own implementation of makeSound()

{% highlight javascript linenos %}
public static void main(String[ ] args) {
  Animal a = new Dog();
  Animal b = new Cat();
}
{% endhighlight %}

Note: Notice how you can use the Animal variable to create a Dog or Cat class.

### Method overriding (runtime polymorphism)

Method overriding refers to creating a unique implementation of a superclass method.

In the example above, Cat and Dog each override the makeSound() method

Rules for Method Overriding (by Sololearn):
- Should have the same return type and arguments
- The access level cannot be more restrictive than the overridden method's access level (Example: If the superclass method is declared public, the overriding method in the sub class can be neither private nor protected)
- A method declared final or static cannot be overridden
- If a method cannot be inherited, it cannot be overridden
- Constructors cannot be overridden

### Method overloading (compile-time polymorphism)

Method overloading refers to creating a method of the same name, but with different parameters.

{% highlight javascript linenos %}

public int getMax(int a, int b) {}

public double getMax(double a, double b) {}

{% endhighlight %}

### Abstraction

"The concept of abstraction is that we focus on essential qualities, rather than the specific characteristics of one particular example."

In Java, abstraction is achieved using abstract classes and interfaces.

These classes CANNOT be instantiated, they must be inherited

{% highlight javascript linenos %}

abstract class Animal {
  int legs = 0;
  abstract void makeSound();
}

class Cat extends Animal {
    public void makeSound() {
        System.out.println("Meow");
    }
}

{% endhighlight %}

Note: The abstract method makeSound() has no implementation

### Interfaces

An interface is an abstract class with ONLY abstract methods. Methods are implicity abstract and public.

May only have static final variables

A class can only extend one superclass, but MANY interfaces. Interfaces can extend interfaces.

{% highlight javascript linenos %}

interface Animal {
    public void eat();
    public void makeSound();
}

class Cat implements Animal {
    public void makeSound() {
        System.out.println("Meow");
    }
    public void eat() {
        System.out.println("omnomnom");
    }
}

{% endhighlight %}

All methods must be overridden.

### Type Casting

Assigning a value of one type (int, for example) to a variable of another type (double, for example)

{% highlight javascript linenos %}

int a = (int) 3.14;

{% endhighlight %}

3.14 was casted to an integer.

#### Upcasting

{% highlight javascript linenos %}

int a = (int) 3.14;

{% endhighlight %}























