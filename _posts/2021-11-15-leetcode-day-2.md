---
layout: post
title:  "Leetcode Day 2"
date:   2021-11-15 17:01:00 -0800
image: leetcode.svg
tags: [leetcode]
featured: "true"
---

~~i def did not skip a day~~

## Question 1: First Bad Version

<div class="ui embed" data-url="https://www.youtube.com/embed/5qap5aO4i9A"></div>

Today I got to solve a problem called [first bad version](https://leetcode.com/problems/first-bad-version/). What you essentially do is try to find which is the bad version given that a function tells you whether or not it is a bad version. All versions after a bad version become bad. For example

`FFTTTTTTT`,

The index at 2 or the 3rd item is bad. All the items after are bad.

`TTTT`,

Works as well. Here all the items are bad since the very first version is bad.

`FT`,
`FFFFFFFFFFT`,

Too. A case of only two items is possible and so is a case where the very last one is the only bad one. There has to be at least 1 bad item

Maybe I got lucky, because the solution is really just binary search again. I just implemented it again using a few more conditions to make sure I got all possible corner cases.

{% highlight python %}
def firstBadVersion(self, n):
    """
    :type n: int
    :rtype: int
    """
    if n == 1:
        return 1
    
    left = 1
    right = n
    while(left <= right):
        print(left, right)
        mid = int((left+right)/2)
        if( not isBadVersion(mid) ):
            left = mid + 1
        else:
            if( mid == 1 ):
                return 1 # this means all the products are bad
            else:
                # check if before is false
                if( not isBadVersion(mid-1) ):
                    return mid
                else:
                    right = mid - 1
{% endhighlight %}

And with that I was able to get the right answer. What I didn't show was the work I did on my paper, but I essentially had to figure out what was important. Like looking back one space... nesting conditions for when you can actually move the right index... etc. Anyways, I'm honestly just surprised it was better than 99% of the solutions. Thought it was pretty normal. Maybe the submissions with like infinite time is the reason it is a top 1 percentile solution.

## Question 2: Largest Divisible Subset

[Here is the next question.](https://leetcode.com/problems/largest-divisible-subset/)

Holy cow this was so hard... I think I need to go back to the drawing board. : 11/16/2021

I will come back in the future...
