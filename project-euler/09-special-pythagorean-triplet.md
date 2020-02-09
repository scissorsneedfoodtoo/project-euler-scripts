# Problem 9: Special Pythagorean triplet

```html
<p>A Pythagorean triplet is a set of three natural numbers, <var>a</var> < <var>b</var> < <var>c</var>, for which, <var>a</var><sup>2</sup> + <var>b</var><sup>2</sup> = <var>c</var><sup>2</sup></p>
<p>For example, 3<sup>2</sup> + 4<sup>2</sup> = 9 + 16 = 25 = 5<sup>2</sup>.</p>
<p>There exists exactly one Pythagorean triplet for which <var>a</var> + <var>b</var> + <var>c</var> = 1000. Find the product <var>abc</var> such that <var>a</var> + <var>b</var> + <var>c</var> = <code>n</code>.</p>
```

* Pythagorean theorem: "When a triangle has a right angle (90 degrees) and squares are made on each of the three sides, then the biggest square has the exact same area as the other two squares put together". a is the shortest side, b is the medium length side, and c is the longest side of the triangle. So if you know the lengths of two sides of the triangle, you can find the length of the third side (as long as it's a right angled triange!)

* Natural numbers: positive integers / whole numbers: 1, 2, 3... and sometimes 0

* Product: the result of multiplying two or more numbers together

```js
function specialPythagoreanTriplet(n) {
  let sumOfabc = n;
  
  for (let a = 1; a <= sumOfabc / 3; a++) {
    for (let b = a + 1; b <= sumOfabc / 2; b++) {
      const c = Math.sqrt(a * a + b * b);
      
      if (a + b + c === sumOfabc) {
        console.log(a, b, c, a * b * c);
        return a * b * c;
      }
    }
  }
}

specialPythagoreanTriplet(24) // 480
// specialPythagoreanTriplet(120) // 49920
// specialPythagoreanTriplet(1000) // 31875000
```
