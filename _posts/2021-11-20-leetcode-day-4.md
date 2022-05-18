---
layout: post
title:  "Leetcode Day 4"
date:   2021-11-20 11:36:00 -0800
image: leetcode.svg
tags: [leetcode]
featured: "true"
---
## Two Sum

Attempt to recall: [Question](leetcode.com/problems/two-sum/) is "Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target."


## Intersection of Two Arrays 

{% highlight cpp %}
vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        vector<int>::iterator it;
        for(int i = 0; i < nums1.size(); i++){
            it = find(nums2.begin(),nums2.end(),nums1[i]);
            if( it != nums2.end() ){
                ans.push_back(nums1[i]);
                *it = -1;
            }
        }
        return ans;
    }
{% endhighlight %}

{% highlight cpp %}
vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
    map<int,int> m;
            vector<int> R;
            for(auto n:nums1) m[n]++;
            // for(const auto& elem : m){
            //     std::cout << elem.first<< " " 
            //       << elem.second << "\n";
            // }
            for(auto n:nums2){
                if( --m[n] >= 0 ){
                    R.push_back(n);
                    
                }
            }
            return R;
}
{% endhighlight %}

## Best Time to Buy and Sell Stock
{% highlight cpp %}
int maxProfit(vector<int>& prices) {
        int index = 0;
        int smallest = INT_MAX;
        int maxprofit = INT_MIN;
        if( prices.size() == 1){
            return 0;
        }
        for(int i = 0; i < prices.size(); i++){
            if(prices[i] < smallest){
                smallest = prices[i];
            }
            if( prices[i] - smallest > maxprofit ) {
                maxprofit = prices[i] - smallest;
            }
        }
        return maxprofit;
    }
{% endhighlight %}