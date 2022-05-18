---
layout: post
title:  "Starting my Leetcode Journey Day 1"
date:   2021-11-13 10:35:00 -0800
image: leetcode.svg
tags: [leetcode]
featured: "true"
---

Okay, so I'm premed who likes to code, so I'm just gonna start now. I did a question yesterday on binary search and I will attempt to answer it again right now.

<div class="ui embed" data-url="https://www.youtube.com/embed/5qap5aO4i9A"></div>

# Binary Search

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

So I got it wrong. I needed left <= right for it to include the arrays/lists are that exactly 1 in length. 

Also, needed to return -1 for the wrong answer.

{% highlight python %}
def binary_search(nums, target):
    left = 0
    right = len(nums) - 1
    while(left <= right): # change here
        mid = int((left+right)/2)
        if( nums[mid] < target ):
            left = mid + 1
        elif( nums[mid] > target ):
            right = mid - 1
        elif( nums[mid] == target ):
            return mid
        else:
            pass
    return -1 # another change here
{% endhighlight %}

# Largest Sum of Nonadjacent Values

Okay, and today I worked on another question. It called the robbery house question, or largest sum of the nonadjacent values. I saw it on TikTok. Essentially, you have a list of numbers or an array of numbers and your goal is to determine the largest sum given any numbers that are not adjacent to each other, where all the numbers are greater than or equal to zero. There's also some other restraints... 

My answer is pseudocode was really not pseudocode here...

{% highlight python %}

if( len(nums) == 0 ):
    return None # I know it's possible to return 0 but I like to get an error
elif( len(nums) == 1 ):
    return nums[1] # Here I definitely know to return the value 
                   # if it's just length 1 list
elif( len(nums) == 2 ):
    return max(nums[0],nums[1]) # just whatever max
else:
    pass # not actually sure what to do here

path1 = nums[0]
path2 = nums[1]

sum1 = generate_path(path1)
sum2 = generate_path(path2) 

def generate_path(nums, i):
    # input list and index
    # iterates through the list to find maximum possible value
    # returns sum

return max(path1,path2)

{% endhighlight %}
and it failed... :(

So I looked up the solution and found out how this is wrong... What it looks like people do is use dynamic programming to contain the largest value as it iterates down the array. What I put, though, is pretty similar I think.

My attempt to recall the solution from memory:
{% highlight python %}
def find_sum(hvals, n): # hvals is the list and n is the length of hvals
    if( n == 0 ):
        return 0
    if( n == 1 ):
        return hvals[0]
    if( n == 2 ):
        return max(hvals[0],hvals[1])
    
    df = [0]*n # create list with same number of zeroes

    for i in range(2,n-3): # start from 3rd value
        df[i] = max(df[i]+hval[i+2],df[i]+hval[i+3])

        #shooooooooooooooot i dont remember...

{% endhighlight %}

oh shit... we had to go back in the list, not forwards...

{% highlight python %}
def find_sum(hvals, n): # hvals is the list and n is the length of hvals
    if( n == 0 ):
        return 0
    if( n == 1 ):
        return hvals[0]
    if( n == 2 ):
        return max(hvals[0],hvals[1])
    
    df = [0]*n # create list with same number of zeroes

    df[0] = hval[0]
    df[1] = max(hval[0],hval[1])

    for i in range(2,n): # start from 3rd value
        df[i] = max(hval[i] + df[i-2], hval[i] + df[i-3])
        # oh shit yeah this makes sense, because now hval at i
        # will always be within the limits of the array
        # I don't have to worry about limits if df's index
        # is the one that changes

    return df[-1] # which means return the last value

{% endhighlight %}

Got it... :)