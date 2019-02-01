# Problem 4 - Largest palindrome product

- What is a palindrome?: A word, number, or phrase that is the same forwards and backwards. So tacocat and the number 

- 1001 are both examples of palindromes.

- Product is just the result of multiplying two or more numbers

```js
function largestPalindromeProduct(n) {
   let largestPalindrome = 0;
   const end = Number(`1e${n}`) - 1;
  
   const isPalindrome = num => {
       const original = num.toString();
       const reversed = original.split('').reverse().join('');
      
       return original === reversed;
   }
  
   for (let i = end; i > 0; i--) {
       for (let j = end; j > 0; j--) {
           const product = i * j;
          
           if (isPalindrome(product) && product > largestPalindrome) {
               // palindromes.push(product);
               largestPalindrome = product;
           }
       }
   }
  
   // const largestPalindrome = Math.max(...palindromes);
   console.log(largestPalindrome);
   return largestPalindrome;
}

largestPalindromeProduct(2);
largestPalindromeProduct(3);
```