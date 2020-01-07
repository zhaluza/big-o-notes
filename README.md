# Big O Notation

## Definition of Big O

We say that an algorithsm is **O(f(n))** if the number of simple operations needed is eventually less than a constant times **f(n)**, as **n** increases.

For example:

- **f(n) = n**: _Linear_
- **(f(n) = n<sup>2</sup>)**: _Quadratic_
- **(f(n) = 1)**: _Constant_
- Etc.

This refers to the **worst-case scenario**: the **upper bound **for runtime.

### Examples

```javascript
function addUpTo(n) {
  return (n * (n + 1)) / 2;
}
```

**Constant: O(1)**
Three operations will always be performed, regardless of the value of `n`.

---

```javascript
function addUpToFirst(n) {
  let total = 0;
  for (let i = 0; i <= n; i++) {
    total += i;
  }
  return total;
}
```

**Linear: O(n)**
Number of operations is bounded by a multiple of `n`

---

```javascript
function countUpAndDown(n) {
  console.log('Going up!');
  for (let i = 0; i < n; i++) {
    console.log(i);
  }
  console.log('At the top!\nGoing down...');
  for (let j = n - 1; j >= 0; j--) {
    console.log(j);
  }
  console.log('Back down. Bye!');
}
```

**Linear: O(n)**
Even though both `for` loops have a time complexity of **2n**, the overall Big O of this algorithm can still be simplified to **O(n)**.

---

```javascript
function printAllPairs(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j < n; j++) {
      console.log(i, j);
    }
  }
}
```

**Quadratic: O(n<sup>2</sup>)**
When an O(n) operation occurs within another O(n) operation — (e.g. a `for` loop nested inside another `for` loop), the overall time complexity is increased to O(n<sup>2</sup>).
