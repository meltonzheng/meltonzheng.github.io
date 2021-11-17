---
layout: post
title:  "Leetcode Day 3"
date:   2021-11-17 14:04:00 -0800
image: leetcode.svg
tags: [leetcode]
featured: "true"
---

Okay, so I tried to take notes but it was so boring. I'd rather do questions. There's this thing called [study plan on leetcode](https://leetcode.com/study-plan/data-structure/) which I'm prolly just gonna follow. I clicked on all three study plans: [algorithms](https://leetcode.com/study-plan/algorithm/) and [dynamic programming (DP)](https://leetcode.com/study-plan/dynamic-programming/). And lemme just say I kinda struggled with the two already for data structures. I started at around 12:30 PM and now it's 2:06 PM. 

# Contains Duplicate 
The first question is [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/). If the array has a duplicate, you return true as in yes there is a duplicate in the array. If the array does not have a duplicate, you return false--there's no duplicate in the array. I used sort and then binary search, which might not be the best answer, but it worked. I think other solutions were just to sort and go through the sorted array.

{% highlight c++ %}
bool containsDuplicate(vector<int>& nums) {
    // can sort then do binary search
    std::sort(nums.begin(),nums.end());
    
    for(int i = 0; i < nums.size(); i++ ){
        if(std::binary_search(nums.begin()+i+1, nums.end(),nums[i])){
            return true;
        }
    }
    return false;
}
{% endhighlight %}
The next question I actually couldn't solve. I looked up the solution
# [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)
So given an array of integers can be + or -, find the subarray that will give you the largest sum. So like
> array(−2, 1, −3, 4, −1, 2, 1, −5, 4)

The answer would be [4,-1,2,1] and you would return 6.

I struggled a lot on this question... but the key idea (at least to me) was to set sum = 0 when you get negative values, so you can keep traversing along the array.. I was trying to save the negative sum so that I can maybe return the negative sum in the end. But to solve that issue is really set the temporary sum to smallest integer possible.

{% highlight c++ %}
int maxSubArray(vector<int>& nums) {
    int sum = 0, smax = INT_MIN;
    for (int num : nums) {
        sum += num;
        smax = max(smax, sum); // See here the the negative sum is still possible.
        if (sum < 0) {
            sum = 0;
        }
    }
    return smax;
}
{% endhighlight %}
I think I should try this question again tomorrow tbh.
Okay, that's it. See you later.