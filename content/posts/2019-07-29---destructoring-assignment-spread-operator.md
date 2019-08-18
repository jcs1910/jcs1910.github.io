---
title: "[JS] Destructuring assignment & Spread Operator"
date: "2019-07-29T20:10:32.169Z"
template: "post"
draft: false
slug: "/posts/destructoring-assignment-spread-operator/"
category: "ES6 Javascript"
tags:
  - "ES6 Javascript"
  - "Destructuring Assignment"
  - "Array Destructuring"
  - "Spread Operator"
description: "The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables."
---

# 1. Destructuring assignment

> The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

## 1) Array Destructing

The keyword you need to remember in destructuring assignment is "unpack". It allows us to unpack arrays or objects into a bunch of variables in a more convenient way.

- An example of how the array is destructured into variables:

```javascript
const number = [1, 2, 3, 4, 5, 6, 7];
const [one, two, ...rest] = number;

console.log(one); //1
console.log(two); //2
console.log(rest); //[3,4,5,6,7]
console.log(typeof rest); //object
```

## 2) Object Destructing

- An example of how the object is destructured into variables:

```javascript
const human = {
  name: "Jason",
  age: 25,
  lastName: "Mraz",
  nationality: "American",
  favPet: {
    dog1: "beagle",
    dog2: "bichon",
    dog3: "collie"
  }
};

const name = human.name; //inefficient
const lastName = human.lastName; //inefficient

const { name, lastName } = human; //object destructuring is more efficient
console.log(name, lastName);

const {
  name,
  lastName,
  nationality: diffName, //when you don't want to use same variable name
  favPet: { dog1, dog2, dog3 }
} = human;
console.log(name, lastName, diffName, dog1, dog2, dog3);
```

The curly bracket of value of favPet `{ dog1, dog2, dog3 }` indicates that it is looking for value inside the favPet, which is equal to `human.favePet.dog1`

There are more examples of destructuring assignments like

- Nested object and array destructuring
- For of iteration and destructuring
- Combined Array and Object Destructuring

# 2. Spread Operator

Spread operator with array/objects is used to make a copy of an existing array/objects or to make a new array/object with more properties.

- Here’s how you can **“combine” two array** and add one more element.

```javascript
// ---Spread Operator
const fruits = ["apple", "banana", "lemon"];
const veges = ["cabbage", "carrot", "tomato"];

let fruitVeg = `I love ${[...fruits, ...veges, "onion"]}`;
console.log(fruitVeg); // I love apple,banana,lemon,cabbage,carrot,tomato,onion
```

- Here’s how you can **“combine” two object** and add one more property `myFourthVege: "onion"`.

```javascript
const objFruits = {
  myFirstFruit: "apple",
  mySecondFruit: "banana",
  myThirdFruit: "lemon"
};

const objVeges = {
  myFirstVege: "cabbage",
  mySecondVege: "carrot",
  myThirdVege: "tomato"
};

const objFruitVeges = { ...objFruits, ...objVeges, myFourthVege: "onion" };
console.log(objFruitVeges);
// myFirstFruit: "apple", mySecondFruit: "banana", myThirdFruit: "lemon", myFirstVege: "cabbage", mySecondVege: "carrot", myThirdVege: "tomato"}
```

Here, the `objFruitVegs` has the existing properties of `objFruits, objVeges` as well as a new property `myFourthVeges`. If you want to extract value from Object, you can use `Object.values().` .It returns an array containing the given object's own enumerable property value.

```javascript
const objFruitVeges = { ...objFruits, ...objVeges, myFourthVege: "onion" };
console.log(Object.values(objFruitVeges));
//["apple", "banana", "lemon", "cabbage", "carrot", "tomato", "onion"]
```

---

## We are creating wealth every time we write a code
