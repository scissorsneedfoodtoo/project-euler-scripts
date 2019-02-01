# Problem 2 - Even Fibbonacci numbers

What is a Fibonacci Number?: Put simply, it’s a famous formula in mathematics. Each number in the sequence is the sum of the two numbers before it. So 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89. (The formula is xn = xn-1 + xn-2) This sequence is really cool because the numbers are found all over nature, like flowers that have 3, 5, 8, 13, or 21 petals, and the numbers have a strong relation to the Golden Ratio and the Golden Rectangle.

```js
function fiboEvenSum(n) {
 let temp, a = 0, b = 1, sum = 0;
   while (n > 0) {
     temp = a;
     a = b;
     b += temp;
     n--;
     if (b % 2 === 0) {
       sum += b;
     }
   }

 console.log(sum);
 return sum;
}

fiboEvenSum(10);
```