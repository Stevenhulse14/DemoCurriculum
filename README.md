# DemoCurriculum

# 🧺 Arrays

## Introduction

Imagine you have a movie watchlist and want to view it on your phone instead of keeping it written down. Then, you want the ability to add, delete, or modify items. How would you achieve this using code? Using a string, number, or boolean wouldn’t quite work. Instead, we need a special data structure called an **array** that allows us to store multiple items in one place.

## 🎯 Learning Objectives

- Understand what an array is and its properties.
- Learn how to create arrays with the array literal syntax.
- Access elements in an array through bracket notation.
- Add and update elements using bracket notation.
- Use methods to add and remove elements from the front or back of an array.
- Iterate over an array.
- Combine functions, conditionals, loops, and arrays.

<hr>

## 🌐 What is an Array?

An array is a data structure that can store multiple values in an ordered collection. You can think of an array as a list that can hold anything—numbers, strings, booleans, objects, or even other arrays. Arrays are **zero-indexed**, meaning the first element starts at index `0`.

Let’s begin by creating an empty array:

```js
const movieWatchlist = [];
console.log(movieWatchlist); // []
```

Arrays have a built-in `.length` property that tells us how many elements are in the array:

```js
console.log(movieWatchlist.length); // 0
```

Arrays can store different types of data, like numbers, strings, booleans, or even other arrays! Though it's common for all elements to be of the same type, that's not a requirement.

```js
const favoriteNumbers = [7, 42, 16, 8];
const randomThings = ["coffee", 42, true, ["apple", "banana"]];
```

Now, let’s create an array for a movie watchlist:

```js
const movieWatchlist = [
  "Inception",
  "The Matrix",
  "Parasite",
  "Interstellar",
  "The Godfather"
];

console.log(movieWatchlist);
```

## 🔍 Accessing Array Elements

Each item in an array has an `index` starting from `0`. To access an element, use square brackets `[]`:

```js
console.log(movieWatchlist[0]); // "Inception"
console.log(movieWatchlist[2]); // "Parasite"
```

If you try to access an index that doesn’t exist, you’ll get `undefined`:

```js
console.log(movieWatchlist[10]); // undefined
```

You can also use expressions or variables to dynamically access elements:

```js
const index = 3;
console.log(movieWatchlist[index]); // "Interstellar"
```

Want to grab the last item in an array dynamically? Use the `.length - 1` trick:

```js
const lastItemIndex = movieWatchlist.length - 1;
console.log(movieWatchlist[lastItemIndex]); // "The Godfather"
```

Why `.length - 1`? Because arrays are zero-indexed, meaning the first element is at position `0`.

## ✏️ Changing Array Elements

You can update array elements by assigning a new value to an index:

```js
movieWatchlist[2] = "The Dark Knight";
console.log(movieWatchlist); 
// ["Inception", "The Matrix", "The Dark Knight", "Interstellar", "The Godfather"]
```

You can also add new elements to the end of the array:

```js
movieWatchlist[movieWatchlist.length] = "Pulp Fiction";
console.log(movieWatchlist); 
// ["Inception", "The Matrix", "The Dark Knight", "Interstellar", "The Godfather", "Pulp Fiction"]
```

## 🔄 Iterating Over an Array

To go through each element in an array, use a `for` loop:

```js
for (let i = 0; i < movieWatchlist.length; i++) {
  console.log(`I want to watch: ${movieWatchlist[i]}`);
}
// I want to watch: Inception
// I want to watch: The Matrix
// I want to watch: The Dark Knight
// I want to watch: Interstellar
// I want to watch: The Godfather
// I want to watch: Pulp Fiction
```

You can also customize how you iterate, like stepping through every other item:

```js
for (let i = 0; i < movieWatchlist.length; i += 2) {
  console.log(`On my priority list: ${movieWatchlist[i]}`);
}
// On my priority list: Inception
// On my priority list: The Dark Knight
// On my priority list: The Godfather
```

You can combine loops, arrays, and conditionals to create more complex behavior:

```js
for (let i = 0; i < movieWatchlist.length; i++) {
  if (i % 2 === 0) {
    console.log(`${movieWatchlist[i]} is an all-time favorite!`);
  } else {
    console.log(`${movieWatchlist[i]} is a recent favorite!`);
  }
}
// Inception is an all-time favorite!
// The Matrix is a recent favorite!
// The Dark Knight is an all-time favorite!
// Interstellar is a recent favorite!
// The Godfather is an all-time favorite!
// Pulp Fiction is a recent favorite!
```

## 🧩 Putting It All Together

Let’s write a function that utilizes loops, conditionals, and arrays:

```js
function checkWatchlist(list, favIndex = 0) {
  console.log(`You have ${list.length} movies on your watchlist.`);
  
  for (let i = 0; i < list.length; i++) {
    if (list[i] === "Inception") {
      console.log("I can't wait to rewatch Inception!");
    } else if (list[i] === "The Godfather") {
      console.log("A classic, I must watch The Godfather soon!");
    } else {
      console.log(`Looking forward to watching ${list[i]}.`);
    }
    
    if (i === favIndex) {
      console.log(`${list[i]} is my favorite movie on the list!`);
    }
  }
}

checkWatchlist(movieWatchlist);
checkWatchlist(movieWatchlist, 4);
```

Before running the code, try predicting the output to better understand how the function works!

## 🚀 Array Methods

JavaScript provides several methods to manipulate arrays efficiently:

1. **`push()`** – Add an element to the end of an array:
   ```js
   movieWatchlist.push("Fight Club");
   console.log(movieWatchlist);
   ```

2. **`pop()`** – Remove the last element of an array:
   ```js
   movieWatchlist.pop();
   console.log(movieWatchlist);
   ```

3. **`unshift()`** – Add an element to the beginning of an array:
   ```js
   movieWatchlist.unshift("Shawshank Redemption");
   console.log(movieWatchlist);
   ```

4. **`shift()`** – Remove the first element of an array:
   ```js
   movieWatchlist.shift();
   console.log(movieWatchlist);
   ```

5. **`splice()`** – Add or remove elements at any position:
   ```js
   movieWatchlist.splice(2, 0, "Gladiator"); // Adds "Gladiator" at index 2
   console.log(movieWatchlist);
   ```

6. **`slice()`** – Copy part of an array into a new array:
   ```js
   const topMovies = movieWatchlist.slice(0, 3); // Copies the first 3 movies
   console.log(topMovies);
   ```

7. **`forEach()`** – Iterate through an array without using a loop:
   ```js
   movieWatchlist.forEach((movie, index) => {
     console.log(`Movie #${index + 1}: ${movie}`);
   });
   ```

8. **`map()`** – Creates a new array by applying a function to every element:
   ```js
   const upperCaseMovies = movieWatchlist.map((movie) => movie.toUpperCase());
   console.log(upperCaseMovies);
   ```

## 🎒 Nested Arrays

Arrays can also store other arrays, which can be useful for grouping data:

```js
const foodOrders = [
  ["pizza", "soda"],
  ["burger", "fries"],
  ["sushi", "green tea"]
];

console.log(foodOrders[0]); // ["pizza", "soda"]
console.log(foodOrders[1][1]); // "fries"
```

---

For more information on arrays and their methods, check out the following resources:

- [MDN Web Docs - Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [JavaScript.info - Arrays](https://javascript.info/array)

Happy coding! 💻
