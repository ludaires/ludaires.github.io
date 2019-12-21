---
layout: post
title:  "Code Challenge @Leetcode - Single-Row Keybord"
location: "New York City"
date:   2019-12-21 
categories: technology
photo: https://ludaires.github.io/img/thinking-code-challenge.jpeg
---
I was doing some code challenges at [Leetcode](https://leetcode.com/problems/single-row-keyboard/){:target="_blank"} using Javascript language, and surprisingly converting the string into array improved the runtime then accessing the character directly via index.

Let me explain in code therms: 

## First ##
Accessing string directly via index `srt[i]` or `str.charAt()` takes at least 60ms. 

```javascript
let str = 'leetcode';
for (let i = 0; i < str; j++) {                  	
		let w = str[i]; // same as str.charAt(i)
		// do some with w
}
```

## Second ##
Converting a string to array improved the runtime to approximately 40ms. Why?   Shouldn’t this method be more time consuming since I'm converting data types?

```javascript
let arr = 'leetcode'.split(''); 
for (let i = 0; i < arr; i++) {                  
		let w = arr[i];   //
		// do some with w
}
```

The same happens when using the spread operator.  

```javascript
let word = [...'leetcode’];
// ['l', 'e', 'e','t', 'c', 'o','d', 'e'] //
```

I’m still looking for an answer to this question. Let me know if you have a clue. ;)



