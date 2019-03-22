```html
<p>Starting in the top left corner of a 2×2 grid, and only being able to move to the right and down, there are exactly 6 routes to the bottom right corner.</p>
<img class="img-responsive center-block" alt="a diagram of 6 2 by 2 grids showing all the routes to the bottom right corner" src="https://i.imgur.com/1Atixoj.gif">
<p>How many such routes are there through a given <code>gridSize</code>?</p>
<script src="index.pack.js"></script>
```

```css
p, img {
  margin: 10px;
}

code {
    color: red;
}
```

```js
// Dynamic programming solution, which is when larger problems are broken down into smaller ones. It's good to use in place of recursion so you can avoid solving the same sub-problem / smaller problem over and over again

function latticePaths(gridSize) {

  let grid = new Array(gridSize + 1).fill(1);
  
  for (let i = 1; i <= gridSize; i++) {
    for (let j = 1; j <= gridSize; j++) {
      // console.log(j - 1, grid[j-1], grid);
      grid[j] += grid[j - 1];
      // console.log(grid);
    }
  }

  console.log(grid.pop());
  return grid.pop();
}

// Combinatorics method, "which is an area of mathematics concerned with counting, and certain properties of finite structures." With the solution above we've really just created Pascal's triangle, and you can use the binomial coefficient to find the right answer. All that said, here's a solution that uses combinatorics to find the number of possible moves.

function latticePaths(gridSize) {
  let paths = 1;

  for (let i = 0; i < gridSize; i++) {
    paths *= (2 * gridSize) - i;
    paths /= i + 1;
    console.log(paths);
  }
  
  return paths;
}

latticePaths(2); // 6
// latticePaths(4); // 70
// latticePaths(9); // 48620
// latticePaths(20); // 137846528820
```
