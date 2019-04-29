---
layout: page
title: Showcasing a Code
subtitle: i.e., project
---

> The term i.e. is a shortening of the Latin expression id est, which translates to “that is.” It is used to introduce a rephrasing or elaboration on something that has already been stated. The term e.g. is an abbreviation of the Latin expression exempli gratia, meaning “for the sake of example” or more colloquially, “for example.” This term is used to introduce examples of something that has already been stated. 
[Source](https://www.dictionary.com/e/whats-the-difference-between-ie-and-eg/)

### Here's how I would showcase projects.

I'll use a previous code I wrote as an example.

{: .box-note}
In number theory, Euler's totient function (phi function) counts the positive integers up to a given integer n that are relatively prime to n. Two integers are said to be relatively prime if the only positive integer (factor) that divides both of them is 1. The totatives of n = 9 are six numbers 1, 2, 4, 5, 7 and 8, so phi(9) = 6 because 3, 6 and 9 are not relatively prime with 9.

{% highlight java linenos %}

        Scanner sc = new Scanner(System.in);
        int input = sc.nextInt();
        sc.close();
        
        String res = "";
        int count = 0;
        
        for (int i=1; i<=input; i++) {
            if (cop(input, i)) {
                res += i + " ";
                count++;
            }
        }
{% endhighlight %}

This code ciphers through digits **i** to **input**, **input** being the number given to the program, and **i** being one of the digits less than **input**. If **input** and **i** are relatively prime, **i** will be logged and the **count** number of relatively prime integers increases.

Here is the **cop()** function.

{% highlight java linenos %}

public static boolean cop(int a, int b) {
        for (int j=2; j<=b; j++) {
            if (a%j==0) {
                if (b%j==0) {
                    return false;
                }
            }
        }
        return true;
    }
{% endhighlight %}

This function checks to make sure **input** and **i** are relatively prime. **j**, a separate local variable is all numbers 2-**i**, **i** being the number that is checked for relative prime. If any number divides both **input** and **i**, we return false.

{: .box-note}
The **i** and **b** variables represent the same value, but in different scopes. Sorry for poor distinction or explanation.

In a larger project, which are the ones I plan to showcase on my main webpage, I obviously wouldn't showcase specific functions and lines as I do here, but rather the overall purpose of the classes and packages I create. This is an example.
