```html
<p>Triangle Number Sequence:</p>
<div class='nums'>
  <p>*<br>1</p>
  <p>*<br>* *<br>2</p>
  <p>*<br>* *<br>* * *<br>3</p>
  <p>*<br>* *<br>* * *<br>* * * *<br>4</p>
  <p>*<br>* *<br>* * *<br>* * * *<br>* * * * *<br>5</p>
</div>

<p>Triangle number formula:</p>
<div class="formula">
  <p>x<sub>n</sub> = n (n + 1) / 2</p>
</div>
```

```css
.nums {
  display: flex;
  text-align: center;
}

.nums p,
.formula {
  margin: 10px;
}
```

```js
function divisibleTriangleNumber(n) {
  let count = 1;
  let triangleNum;

  const genFactors = num => {
    let factors = [];

    for (let i = 1; i <= Math.sqrt(num); i++) {
      if (num % i === 0) {
        factors.push(i);
        if (num / i !== i) {
          factors.push(num / i);
        }
        // console.log(num, i, num / i);
      }
    }
    // console.log(factors.sort((a, b) => a - b));
    return factors;
  };

  while (genFactors(triangleNum).length < n) {
    triangleNum = count * (count + 1) / 2;
    // console.log(count, triangleNum);
    count++;
  }

  console.log(triangleNum);
  return triangleNum;
}

divisibleTriangleNumber(5); // 28
// divisibleTriangleNumber(10); // 120
// divisibleTriangleNumber(23); // 630
// divisibleTriangleNumber(167); // 1385280
// divisibleTriangleNumber(374); // 17907120
// divisibleTriangleNumber(500); // 76576500
```