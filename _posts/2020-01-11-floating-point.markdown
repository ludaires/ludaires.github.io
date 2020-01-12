---
layout: post
title:  "Javascript: Floating Point Arithmetic"
location: "New York City"
date:   2020-01-11 
categories: technology
photo: https://ludaires.github.io/img/overflow-error.jpeg
---
Javascript case 
- Why the numbers below don't add up to a nice round 0.3?

```node
	> 0.1 + 0.2
	0.30000000000000004
	>
```

You got a unexpected result:
```
0.30000000000000004
```

Maybe you asked for help on some forum and got pointed to a *long article with lots of formulas* that didn’t see to help with your problem. Today I'm here to:

1 . Explain concisely why you get that unexpected result  
2 . Tell you know to deal with this problem   
3 . If you’re interested, provide in-depth explanations of why   floating point number have to work like that and what other problems can arise. You must look at this [site](https://floating-point-gui.de/)
	

Internally, computers use a format ([binary](https://floating-point-gui.de/formats/binary/), [floating-point](https://floating-point-gui.de/formats/fp/)) that can not accurately represent a number like 0.1, 0.2 or 0.3 at all.

When the code is compiled or interpreted, your “0.1” is already rounded to the nearest number in that format, which results in a small [rounding error](https://floating-point-gui.de/errors/rounding/) even before the calculation happens.

**Why do computers use such a stupid system?** 

It’s not stupid, just different. Decimal numbers cannot accurately represent a number like 1/3, so you have to round to something like 0.33 - and you don’t expect 0.33 + 0.33 + 0.33 to add up to 1, either - do you?

Computers use [binary numbers](https://floating-point-gui.de/formats/binary/) because they’re faster at dealing with those, and because for most calculations, a tiny error in the 17th decimal place doesn’t matter at all since the numbers you work with aren’t round (or that precise) anyway.

**What can I do to avoid this problem?**

That depends on what kind of calculations you’re doing.

* If you really need your results to add up exactly, especially when you work with money: use a special [decimal datatype](https://floating-point-gui.de/formats/exact/).
* If you just don’t want to see all those extra decimal places: simply format your result rounded to a fixed number of decimal places when displaying it.
* If you have no decimal datatype available, an alternative is to work with [integers](https://floating-point-gui.de/formats/integer/), e.g. do money calculations entirely in cents. But this is more work and has some drawbacks.

**Why do other calculations like 0.1 + 0.4 work correctly?**

In that case, the result (0.5) can be represented exactly as a floating-point number, and it’s possible for rounding errors in the input numbers to cancel each other out - But that can’t necessarily be relied upon (e.g. when those two numbers were stored in differently sized floating point representations first, the rounding errors might not offset each other).

In other cases like 0.1 + 0.3, the result actually isn’t really 0.4, but close enough that 0.4 is the shortest number that is closer to the result than to any other floating-point number. Many languages then display that number instead of converting the actual result back to the closest decimal fraction.


### Floating-Point Cheat Sheets for Javascript ###

**Round Types** 


```node
> var num = 0.1 + 0.2
 0.30000000000000004
> Math.round(num)
 0
> Math.round(num * 10000000) / 10000000
 0.3
```
```
Math.round
```
The round method rounds to the nearest integer: 3.1 becomes 3, 3.6 becomes 4 and -1.1 becomes -1.

``` node
> Math.ceil(num)
 1
> Math.floor(num)
 0
```
Math.ceil() rounds up: 3.1 becomes 4, and -1.1 becomes -1.
Math.floor() rounds down: 3.1 becomes 3, and -1.1 becomes -2.

If you want to decide how many values after comman, there is a toPrecise() method to do it. The toPrecision() method returns a string representing the Number object to the specified precision.
The toFixed() method formats a number using fixed-point notation.

``` node
> num.toPrecision(2)
'0.3'
> +num.toPrecision(2)
0.3
> parseFloat(num.toPrecision(2))
0.3

> +num.toFixed(2)
0.3
```

**References**      
[Math.round() MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round)       
[toPrecision()MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toPrecision)       
[toFixed() MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)  
[Numbers - Javascript Info](https://javascript.info/number)


