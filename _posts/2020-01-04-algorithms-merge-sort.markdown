---
layout: post
title:  "Algorithms: Merge Sort and Recursion"
location: "New York City"
date:   2020-01-04 
categories: technology
photo: https://ludaires.github.io/img/recursion.jpeg
---
## Merge Sort 

Merge Sort is on of the most efficient sorting algorithms. It works on the principle of Divide and Conquer. Merge sort repeatedly breaks down a list into several sublist until each sublist consist of a single element and merging those sublist in a manner that results into a sorted list. 

**Implementation in Pseudo Code** 
```
	 - Sort the left half of the array (assuming n > 1)      
	 - Sort the right half of the array (assuming n >1)  
	 - Merge the two halves together
```

### Time Complexity ###

Worst-case scenario: We have to split n elements up and then recombine them, effectively doubling the sorted subarrays as we build them up. (Combining sorted 1-element arrays into 2-element array, combining
sorted 2-element arrays into 4-element arrays…)  ( O (n log n) )

Best-case scenario: The array is already perfectly sorted. But we still have to split and recombine it back together with this algorithm. ( Ω (n log n) )

Merge sort uses something called recursion.  Recursion is an extremely useful technique. Let's quickly review what it is. 

## Recursion

The definition of recursive functions is one that, as part of its execution, invokes itself.  Every recursive function has two cases that could apply, given any input.

**The Base Case**

The base case is a problem that you either already know the answer to, or can solve using some other method.
Note that a recursive algorithm may have more than one base case, but they are all lumped together under this heading.

**The Recursive Case**

The recursive case is a problem that can be broken down into “smaller” pieces which can be solved individually. The solutions are then combined into the answer for the whole problem.

Note that the recursive case **must** move towards the base, by reducing the ``size’’ of the problem. If it doesn’t, then the base case will never be reached, and the algorithm will not terminate.

Note again that a recursive algorithm may have more than one recursive case (i.e. it may recurse more than once, binary tree traversal algorithms are a good example of this).

Code Example

```javascript 
	const factorial = (n) => {
		if ( n === 1 ) {
			return 1;
		} else { 
			return n * factorial ( n - 1 );
		}
	}
```

In general, recursive functions replace loops in non-recursive functions. 

**References**      
[Recursion by CS50](https://youtu.be/mz6tAJMVmfM)       
[CS50 Algorithm Review Notes](http://ellard.org/dan/www/CS50-96/Notes/alg.html#sorting-def)       
[Merge Sort by CS50](https://youtu.be/Ns7tGNbtvV4)  
[Merge Sort by InterviewBit](https://www.interviewbit.com/tutorial/merge-sort-algorithm/)  



