# JSPractice

JavaScript small problems

# 1.

```javascript
console.log(1);
const promise = new Promise((resolve) => {
  console.log(2);
  resolve();
  console.log(3);
});

console.log(4);

promise
  .then(() => {
    console.log(5);
  })
  .then(() => {
    console.log(6);
  });

console.log(7);

setTimeout(() => {
  console.log(8);
}, 10);

setTimeout(() => {
  console.log(9);
}, 0);

// Ans : 1,2,3,4,7,5,6,9,8
```

---

# 2.
```javascript
new Promise((resolve, reject) => {
    resolve(1)
    resolve(2)
    reject('error')
  }).then((value) => {
    console.log(value)
  }, (error) => {
    console.log('error')
  })

  // Ans : 1
```