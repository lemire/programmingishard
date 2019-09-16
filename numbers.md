## Fixed-bit numbers


integers wrap or not

two's complement, division, modulo and all that

floating point numbers are not associative

can you represent the world GDP using a float in JavaScript?


Multiplying by the inverse is not the same as the division https://lemire.me/blog/2019/03/12/multiplying-by-the-inverse-is-not-the-same-as-the-division/


Round off errors and the Patriot missile
https://autarkaw.org/2008/06/02/round-off-errors-and-the-patriot-missile/

https://randomascii.wordpress.com/category/floating-point/



What does « a == b » mean?


if a is an integer, a * -1 may not be well-defined



These two differs...

```
x -= y
x += -y
```



(credit : Travis Downs)


Integer not associative `a + (b + c)` is not `(a + b) + c`. (credit: Steve Canon)


Whether in signed or unsigned mode, the negation is -x is ~x+1. That's because x+~x is 0xFFFFFF...FF.

```
function zigzag_encode(val) {
  return (val + val) ^ (val >> 31);;
}

function zigzag_decode(val) {
  return  (val >> 1) ^ (- (val & 1));
}
```
