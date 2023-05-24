# vanilla-js-bangla-currency-converter
This JavaScript function converts numbers to words in Bangla.

## Usage

To use this function, simply call `inWordsBn()` with the desired number as an argument. For example, `inWordsBn(12365.25)` would return "বার হাজার তিনশত পঁয়ষট্টি টাকা পঁচিশ পয়সা মাত্র।".

```js
const amount = 12365.25;
const amountInWords = inWordsBn(amount);
console.log(amountInWords); // বার হাজার তিনশত পঁয়ষট্টি টাকা পঁচিশ পয়সা মাত্র।
```

## Credits
The code has been taken from https://github.com/mijaved/jsUtil/blob/master/AmountInWord/amountInWord_bn.js, I have only made a small modification to include paisa.
All credit for this code goes to https://github.com/mijaved/. Thank you for providing such a useful utility!
