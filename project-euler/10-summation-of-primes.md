# Problem 10: Summation of primes

- A prime number is a whole number greater than 1 whose only factors are 1 and itself (2, 3, 5, 7, 11, 13, 17, 19, 23..) -- In other words, it's a number greater than 1 that can not be made by multiplying other whole numbers

```js
function primeSummation(n) {
  // let total = 0;
  const primes = [];
  
  const isPrime = num => {
    for (let i = 2; i <= Math.sqrt(num); i++) {
      if (num % i === 0) {
        return false;
      }
    }
    return num !== 0 && num !== 1;
  }
  
  for (let i = 2; i < n; i++) {
    if (isPrime(i)) {
      // total += i;
      primes.push(i);
    }
  }
  
  const total = primes.reduce((acc, curr) => {
    return acc += curr;
  }, 0);
  
  console.log(total);
  return total;
}

primeSummation(17); // 41
// primeSummation(2001); // 277050
// primeSummation(140759); // 873608362
// primeSummation(2000000); // 142913828922

// https://www.freecodecamp.rocks/learn/coding-interview-prep/project-euler/problem-10-summation-of-primes
```
