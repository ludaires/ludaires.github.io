---
layout: post
title:  "Two Sum: Improving Time Complexity"
location: "New York City"
date: 2020-01-25 
categories: technology
photo: https://ludaires.github.io/img/two-sum.png
---
## Two Sum ##
Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.
You may assume that each input would have **exactly** one solution, and you may not use the *same* element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9.   
Because nums[0] + nums[1] = 2 + 7 = 9,    
return [0,1]

### Implementation ### 
```js
var twoSum = function(nums, target) {
     for (let i = 0; i < nums.length; i++) {
         for(let j = i + 1; j < nums.length; j++) {
             if (nums[j] === (target - nums[i])) {
                 return [i, j]; 
             }
         }
     }
 }
```
In this first example the time complexity is quadratic  O(n^2). I made one loop inside of a loop to search for all possible pairs of numbers. 

Time complexity: O(n^2). For each element, we try to find its complement by looping through the rest of array which takes O(n) time. Therefore, the time complexity is O(n^2).

```js
var twoSum = function(nums, target) {
    const numbers = {}
    for (let i = 0; i < nums.length; i++) {
        if(numbers[target - nums[i]] !== undefined ) {
            return [numbers[target - nums[i]], i];
        }
        numbers[nums[i]] = i;
    }
};
```
In this example, I do two things at once. I iterate and insert elements into the table (numbers). 

Time complexity: O(n). We traverse the list containing n
elements only once. Each look up in the table costs only O(1) time.

**References**      
[Example Coding/Engineering Interview](https://www.youtube.com/watch?v=XKu_SEDAykw) 
