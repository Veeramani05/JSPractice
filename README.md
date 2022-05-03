# JSPractice

JavaScript small problems

<style>
    *{
        padding: 0;
        margin: 0;
        font-family: Consolas;
    } 
</style>

#1.

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
```
_Ans: 1,2,3,4,7,5,6,9,8_

---
