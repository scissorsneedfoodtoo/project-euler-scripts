```js
function longestCollatzSequence(limit) {
  let longestSequenceLength = 0;
  let startingNum = 0;
  
  const getSequenceLength = num => {
    let sequence = [num];
    
    while (num > 1) {
      if (num % 2 === 0) {
        num = num / 2;
      } else {
        num = num * 3 + 1;
      }
      sequence.push(num);
    }
    // console.log(sequence);
    return sequence.length;
  }
  
  for (let i = 2; i < limit; i++) {
    if (getSequenceLength(i) > longestSequenceLength) {
      longestSequenceLength = getSequenceLength(i);
      startingNum = i;
    }
  }
  
  console.log(startingNum);
  return startingNum;
}

// https://www.freecodecamp.rocks/learn/coding-interview-prep/project-euler/problem-14-longest-collatz-sequence
```
