# Joyful JavaScript
Easy-to-follow code snippets of JavaScript

## Array functions

### Methods

#### Reduce
The `reduce()` function is great for reducing an array into a single value.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesSum = carPrices.reduce((accumulator, price) => accumulator + price);

console.log(carPricesSum); // Output: 175000
```

#### Map
The `map()` function can be used to apply a calculation to each element in an array.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(price => price * 1.05);

console.log(carPricesAfterTax); // Output: [31000, 42500, 27500, 82500]
```

#### Filter
The `filter()` function can be used to filter out elements.

```javascript
const fancyCars = carPrices.filter(price => price >= 50000);

console.log(fancyCars); // Output: [50000, 75000]
```

### Chaining Array Functions

Now let's have some fun! We can combine our array functions in interesting ways. Let's try to chain together
the `map()` and `reduce()` functions.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(price => price * 1.05)
                                   .reduce((accumulator, price) => accumulator + price);

console.log(carPricesAfterTax); // Output: 189000
```

Now we are cooking! We can separate out the callback functions to make things a little easier to read.


```javascript
const addSalesTax = price => price * 1.05;
const sumPrices = (accumulator, price) => accumulator + price;

const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(addSalesTax)
                                   .reduce(sumPrices);

console.log(carPricesAfterTax); // Output: 189000
```
Ah, pure bliss.
