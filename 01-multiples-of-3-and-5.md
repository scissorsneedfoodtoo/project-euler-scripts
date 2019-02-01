# Problem 1 - Multiples of 3 and 5

Natural number: the positive integers (whole numbers) 1, 2, 3, etc., and sometimes zero as well.

Multiple: A multiple is the result of multiplying a number by an integer (not a fraction). Ex: 15 is a multiple of 3 (3 x 5 = 15).

Another definition of multiple: a number that can be divided by another number without a remainder.

```js
function multiplesOf3and5(number) {
 let total = 0;
  for (let i = 0; i < number; i++) {
   if (i % 3 === 0 || i % 5 === 0) {
     total += i;
   }
 }

 console.log(total);
 return total;
}

multiplesOf3and5(1000);
```