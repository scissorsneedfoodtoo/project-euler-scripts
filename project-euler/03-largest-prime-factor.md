# Problem 3 - Largest prime factor

- "Factors" are the numbers you multiply together to get another number (Factors of 18: 1, 2, 3, 6, 9, 18)

- A prime number is a whole number greater than 1 whose only factors are 1 and itself (2, 3, 5, 7, 11, 13, 17, 19, 23..)

- Prime factors are factors that also happen to be prime numbers (Prime factors of 18: 2 and 3 -- 2 * 3 * 3)

```js
function largestPrimeFactor(number) {
   let largestPrime = 0;
  
   const isPrime = num => {
       for(let i = 2; i < num; i++) {
           if(num % i === 0) {
               return false;
           }
       }
       return num !== 0 && num !== 1;
   }

   for (let i = 1; i <= number; i++) {
       // console.log(i, number % i);
       if (number % i === 0 && isPrime(i)) {
           // console.log(isPrime(i));
           largestPrime = i;
       }
   }
  
   console.log(largestPrime);
   return largestPrime;
}

largestPrimeFactor(18);
// largestPrimeFactor(13195);
```
