# Joyful JavaScript
Easy-to-follow code snippets of JavaScript

## Array methods

### Methods

#### Reduce
The `reduce()` method is great for reducing an array into a single value.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesSum = carPrices.reduce((accumulator, price) => accumulator + price);

console.log(carPricesSum); // Output: 175000
```

#### Map
The `map()` method can be used to apply a calculation to each element in an array.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(price => price * 1.05);

console.log(carPricesAfterTax); // Output: [31000, 42500, 27500, 82500]
```

#### Filter
The `filter()` method can be used to filter out elements.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const fancyCars = carPrices.filter(price => price >= 50000);

console.log(fancyCars); // Output: [50000, 75000]
```

#### Some
The `some()` method can be used to check if at least one element meets a given condition. If the condition is met for at least one element, `true` is returned; otherwise, `false` is returned.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const hasFancyCars = carPrices.some(price => price >= 50000);

console.log(hasFancyCars); // Output: true
```

#### Every
The `every()` method can be used to check if all elements meet a given condition. If the condition is met for all the elements, `true` is returned; otherwise, `false` is returned.

```javascript
const carPrices = [90000, 50000, 100000, 75000];
const areAllCarsFancy = carPrices.every(price => price >= 50000);

console.log(areAllCarsFancy); // Output: true
```

### Chaining Array Functions

Now let's have some fun! We can combine our array methods in interesting ways. Let's try to chain together the `map()` and `reduce()` methods.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(price => price * 1.05)
                                   .reduce((accumulator, price) => accumulator + price);

console.log(carPricesAfterTax); // Output: 189000
```

Now we are cooking! We can separate the callback functions to make things a little easier to read.

```javascript
const addSalesTax = price => price * 1.05;
const sumPrices = (accumulator, price) => accumulator + price;

const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(addSalesTax)
                                   .reduce(sumPrices);

console.log(carPricesAfterTax); // Output: 189000
```
Ah, pure bliss.

## Conditionals

### Optional Chaining

You can use optional chaining to tell whether an object or property exists in an object. This is handy for avoiding errors.

```javascript
const user = {name: 'Alice', address: null};
const street = user.address?.street || 'Unknown';

console.log(street); // Output: 'Unknown'
```

## Closures

You can use closures to keep data private and maintain it in a persistent state, which is useful for data encapsulation and efficient memory utilization. This data remains in memory even after the function has been executed, and it stays there until the closure is no longer referenced or the program completes.

```javascript
const createIdGenerator = () => {
  let id = 0;  // This variable is in the outer function's scope

  return () => {
    id += 1;  // This inner function accesses and modifies 'id'
    return id;
  };
};

const generateId = createIdGenerator();  // The function 'generateId' is a closure

console.log(generateId());  // Outputs: 1
console.log(generateId());  // Outputs: 2
console.log(generateId());  // Outputs: 3
```

## Memoization

By memoizing functions, you can cache the results of functions that are expensive to compute or frequently called with the same inputs, making your programs faster and more efficient by reducing unnecessary calculations.

```javascript
const memoize = (fn) => {
  const cache = {};

  return (num) => {
    if (cache[num] !== undefined) { 
      console.log(`Cached result for: ${num}`); 
      return cache[num];  // Return cached result if it exists
    } else {
      console.log(`Computing result for: ${num}`); 
      const result = fn(num);  // Compute the result if not cached
      cache[num] = result;  // Store the computed result in the cache
      return result;
    }
  };
};

const square = (num) => num * num;

const memoizedSquare = memoize(square);  // Create a memoized version of the square function

console.log(memoizedSquare(4));  // Outputs: Computing result for: 4 -> 16
console.log(memoizedSquare(4));  // Outputs: Cached result for: 4 -> 16
```
