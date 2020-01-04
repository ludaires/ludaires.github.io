---
layout: post
title:  "Algorithms: Merge Sort and Recursion"
location: "New York City"
date:   2019-01-04 
categories: technology
photo: https://ludaires.github.io/img/recursion.jpeg
---
....in progress 
<!-- 
Time complexity is the number of operations an algorithm performs to complete its task. The algorithm that performs the task in the smallest number of operations is considered the most efficient one in terms of the complexity. It is important to point out that the time complexity are also affected by factors such as your operations system and hardware. 

## Linear Search ##
Linear search is used on a collection of items. It relies on the technique of traversing a list from start  to end trying to find the target element. 

**Implementation in pseudo code**
```
	- Repeat, starting at the first element:
		- if the first element is what you’re looking for (the target), stop.
		- Otherwise, move to the next element.
```


### Time complexity of Linear Search ###

Worst-case scenario: I have to look through the entire array of n elements, either because the target element is the last element of the array or doesn’t exist in the array at all. O(n)

Best-case scenario: The target element is the first element of the array, and so I can stop looking immediately after we start.

## Binary Search ##

Binary search is the most popular Search algorithm. It is efficient and also one of the most commonly used techniques that is used to solve problems. The collection must first be sorted, else I can not make assumptions about the array’s contents.  

Fun fact: A study from 1988 showed that only one in four textbooks has a correct implementation of binary search (that might be much better now) but it shows that it’s very easy to make a mistake during implementation. 

In binary search, the idea is divide and conquer, reducing the search area by half each time, trying to find the target. 

**Implementation in pseudo code:** 
```
	- Repeat until the (sub)array is of size 0:
		- calculate the middle point of the current (sub)array.
		- if the target is at the middle, stop
		- otherwise, if the target is less than what’s at the middle, repeat, changing the end point to be just to the left of the middle
		- otherwise, if the target is greater than what’s at the middle, repeat, changing the start point to be just to the right of the middle. 
```

Most implementations calculate the middle point using the formula m = (start + end)/2. The issue here is that the sum of start plus end might overflow. 
That’s can happen because, for example, in C++ and Java, int types fits values up to around 2 billion (2^31). If you add two such values, the sum will overflow and you might have some mistake because of that. It will not compute the average correctly.  

The best formula to get the middle would be m = start + (end - start/2). Assuming that start and end are non-negative number.

### Time complexity of Binary Search ###

Wort-case scenario: I have to divide a list of elements in half repeatedly to find the target element, either because the target element will be found at the end of the last division or doesn’t exist in the array at all. (O(log n) ).

Best-case scenario: The target element is at the midpoint of the full array, and so I can stop looking immediately after I start. 

**Algorithms Summary** 

<iframe width="560" height="315" src="https://www.youtube.com/embed/ktWL3nN38ZA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**References**      
[Linear Search by CS50](https://www.youtube.com/watch?v=TwsgCHYmbbA)       
[Linear Search Algorithms by HackerEarth](https://www.hackerearth.com/practice/algorithms/searching/linear-search/practice-problems/)       
[Binary Search lecture (C++ and Python) by Errichto](https://www.youtube.com/watch?v=GU7DpgHINWQ)  
[Binary Search by CS50](https://www.youtube.com/watch?v=T98PIp4omUA)   -->