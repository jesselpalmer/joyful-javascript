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
const fancyCars = carPrices.filter(price => price >= 50000);

console.log(fancyCars); // Output: [50000, 75000]
```

### Chaining Array Functions

Now let's have some fun! We can combine our array methods in interesting ways. Let's try to chain together
the `map()` and `reduce()` methods.

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

You can use closures to keep data private and maintain it in a persistent state, which is useful for data encapsulation and efficient memory utilization. 
This data remains in memory even after the function has been executed, and it stays there until the closure is no longer referenced or the program completes.

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
