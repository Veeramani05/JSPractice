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

# 2.

```javascript
new Promise((resolve, reject) => {
  resolve(1);
  resolve(2);
  reject("error");
}).then(
  (value) => {
    console.log(value);
  },
  (error) => {
    console.log("error");
  }
);

// Ans : 1
```

```javascript
Promise.resolve(1)
  .then(() => 2)
  .then(3)
  .then((value) => value * 3)
  .then(Promise.resolve(4))
  .then(console.log);

// Ans : 6
```

```javascript
Promise.resolve(1)
  .then((val) => {
    console.log(val); // 1
    return val + 1;
  })
  .then((val) => {
    console.log(val); // 2
  })
  .then((val) => {
    console.log(val); // undefined
    return Promise.resolve(3).then((val) => {
      console.log(val); // 3
    });
  })
  .then((val) => {
    console.log(val); // undefined
    return Promise.reject(4);
  })
  .catch((val) => {
    console.log(val); // 4
  })
  .finally((val) => {
    console.log(val); // undefined
    return 10;
  })
  .then((val) => {
    console.log(val); // undefined
  });

// Ans: 1,2,undefined, 3,undefined,4, undefined, undefined
```

```javascript
for (var i = 0; i < 5; i++) {
  setTimeout(() => console.log(i), 0); // 5,5,5,5,5
}
// Ans: 5,5,5,5,5
for (let i = 0; i < 5; i++) {
  setTimeout(() => console.log(i), 0); // 0,1,2,3,4
}
//Ans : 0,1,2,3,4
```

```javascript
const obj = {
  dev: "VEERA",
  a: function () {
    return this.dev; // VEERA
  },
  b() {
    return this.dev; // VEERA
  },
  c: () => {
    return this.dev; // undefined
  },
  d: function () {
    return (() => {
      return this.dev; // VEERA
    })();
  },
  e: function () {
    return this.b(); // VEERA
  },
  f: function () {
    return this.b; // function declaration
  },
  g: function () {
    return this.c(); // undefined
  },
  h: function () {
    return this.c; // function statement
  },
  i: function () {
    return () => {
      return this.dev; // undefined
    };
  },
};

console.log(obj.a()); // VEERA
console.log(obj.b()); // VEERA
console.log(obj.c()); // undefined
console.log(obj.d()); // VEERA
console.log(obj.e()); // VEERA
console.log(obj.f()()); // VEERA
console.log(obj.g()); // undefined
console.log(obj.h()()); // undefined
console.log(obj.i()()); // undefined
```

```javascript
let a = 1;
const b = ++a;
const c = a++;
console.log(a); // 3
console.log(b); // 2
console.log(c); // 2
//Ans : 3,2,2
```
