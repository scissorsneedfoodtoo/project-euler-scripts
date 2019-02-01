# Problem 5 - Smallest multiple

- What’s a multiple?: A number that can be divided by another number without a remainder. Or conversely, it’s the result of multiplying a number by a whole number. So the multiples of 3 are 3, 6, 9, 12, 15, 18, and etc.

```js
function smallestMult(n) {
 const isDivisible = number => {
   for (let i = 1; i <= n; i++) {
     if (number % i !== 0) {
       return false;
     }
   }

   return true;
 }

 let currentNum = n;

 while (!isDivisible(currentNum)) {
     currentNum += n;
 }
  console.log(currentNum);
 return currentNum;
}
smallestMult(5);
smallestMult(7);
smallestMult(10);
smallestMult(13);
smallestMult(20);


const t0 = performance.now();
smallestMult(20)
const t1 = performance.now();

console.log("smallestMult took " + (t1 - t0) + " milliseconds.")
```
