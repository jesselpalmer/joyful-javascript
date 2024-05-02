# Joyful JavaScript
Easy-to-follow code snippets of JavaScript

## Array methods

### Reduce
The `reduce()` function is great for reducing an array into a single value.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesSum = carPrices.reduce((accumulator, price) => accumulator + price, 0);

console.log(carPricesSum); // Output: 175000
```

### Map
The `map()` function can be used to apply a calculation to each element in an array.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesAfterTax = carPrices.map(price => price * 1.05);
console.log(carPricesAfterTax); // Output: [31000, 42500, 27500, 82500]
```
