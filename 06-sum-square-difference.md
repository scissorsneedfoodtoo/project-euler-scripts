# Problem 6: Sum square difference script

Natural number: A non-negative integer, so any positive whole number, which, depending on the definition, either starts from 0 or from 1. For this problem we’ll be starting from 1.

```js
function sumSquareDifference(n) {
   const sumOfSquares = () => {
       let total = 0;
       for (let i = 1; i <= n; i++) {
           total += (i ** 2);
       }
       return total;
   }
  
   const squareOfSum = () => {
       let total = 0;
       for (let i = 1; i <= n; i++) {
           total += i;
       }
       return total ** 2;
   }
  
   const answer = squareOfSum() - sumOfSquares();
   console.log(answer);
   return answer;
}

sumSquareDifference(10) // 2640
// sumSquareDifference(20) // 41230
// sumSquareDifference(100) // 25164150
```
