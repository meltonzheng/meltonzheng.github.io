---
layout: post
title:  "Starting my Leetcode Journey"
date:   2021-11-13 10:35:00 -0800
categories: leetcode
---

Okay, so I'm premed who likes to code, so I'm just gonna start now. I did a question yesterday on binary search and I will attempt to answer it again right now.

{% highlight python %}
def binary_search(nums, target):
    left = 0
    right = len(nums) - 1
    while(left < right):
        mid = int((left+right)/2)
        if( nums[mid] < target ):
            left = mid + 1
        elif( nums[mid] > target ):
            right = mid - 1
        elif( nums[mid] == target ):
            return mid
        else:
            pass
{% endhighlight %}

Something like that I think.... let me double check