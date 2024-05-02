# Joyful JavaScript
Easy-to-follow code snippets of JavaScript

## Reduce
The `reduce()` function is great for reducing an array into single-value.

```javascript
const carPrices = [30000, 50000, 25000, 75000];
const carPricesSum = carPrices.reduce((accumulator, price) => accumulator + price, 0);

console.log(carPricesSum); // Output: 175000
```
