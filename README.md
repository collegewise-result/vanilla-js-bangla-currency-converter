# vanilla-js-bangla-currency-converter
This JavaScript function converts numbers to words in Bangla.

## Code
```js
function inWordsBn(num) {
    //declear variables
    var BnNumbers=["","এক","দুই","তিন","চার","পাঁচ","ছয়","সাত","আট","নয়","দশ","এগার","বার","তের","চৌদ্দ","পনের ","ষোল","সতের","আঠার","ঊনিশ","বিশ","একুশ","বাইশ","তেইশ","চব্বিশ","পঁচিশ","ছাব্বিশ","সাতাশ","আটাশ","ঊনত্রিশ","ত্রিশ","একত্রিশ","বত্রিশ","তেত্রিশ","চৌত্রিশ","পঁয়ত্রিশ","ছত্রিশ","সাঁইত্রিশ","আটত্রিশ","ঊনচল্লিশ","চল্লিশ","একচল্লিশ","বিয়াল্লিশ","তেতাল্লিশ","চুয়াল্লিশ","পঁয়তাল্লিশ","ছেচল্লিশ","সাতচল্লিশ","আটচল্লিশ","ঊনপঞ্চাশ","পঞ্চাশ","একান্ন","বায়ান্ন","তিপ্পান্ন","চুয়ান্ন","পঞ্চান্ন","ছাপ্পান্ন","সাতান্ন","আটান্ন","ঊনষাট","ষাট","একষট্টি","বাষট্টি","তেষট্টি","চৌষট্টি","পঁয়ষট্টি","ছেষট্টি","সাতষট্টি","আটষট্টি","ঊনসত্তর","সত্তর","একাত্তর","বাহাত্তর","তিয়াত্তর","চুয়াত্তর","পঁচাত্তর","ছিয়াত্তর","সাতাত্তর","আটাত্তর","ঊনআশি","আশি","একাশি","বিরাশি","তিরাশি","চুরাশি","পঁচাশি","ছিয়াশি","সাতাশি","আটাশি","ঊননব্বই","নব্বই","একানব্বই","বিরানব্বই","তিরানব্বই","চুরানব্বই","পঁচানব্বই","ছিয়ানব্বই","সাতানব্বই","আটানব্বই","নিরানব্বই",];
    var BnTens=["","","বিশ","ত্রিশ","চল্লিশ","পঞ্চাশ","ষাট","সত্তর","আশি","নব্বই",]
    
      //convert to number
    num = parseFloat(num);

    //find whole number and decimal part for finding paisa.
    let wholeNumber = Math.floor(num);
    let decimalPart = (num - wholeNumber).toFixed(2).substring(2);

    if ((wholeNumber = wholeNumber.toString()).length > 9) return "overflow";
    n = ("000000000" + wholeNumber)
      .substr(-9)
      .match(/^(\d{2})(\d{2})(\d{2})(\d{1})(\d{2})$/);
    if (!n) return;
    
    //find paisa
    let paisaInWord = "";
    if (decimalPart > 0) {
      paisaInWord = BnNumbers[parseInt(decimalPart)] + " পয়সা ";
    }

    var str = "";
    str +=
      n[1] != 0
        ? (BnNumbers[Number(n[1])] || BnTens[n[1][0]] + " " + a[n[1][1]]) + " কোটি "
        : "";
    str +=
      n[2] != 0
        ? (BnNumbers[Number(n[2])] || BnTens[n[2][0]] + " " + a[n[2][1]]) + " লাখ "
        : "";
    str +=
      n[3] != 0
        ? (BnNumbers[Number(n[3])] || BnTens[n[3][0]] + " " + a[n[3][1]]) + " হাজার "
        : "";
    str +=
      n[4] != 0
        ? (BnNumbers[Number(n[4])] || BnTens[n[4][0]] + " " + a[n[4][1]]) + "শত "
        : "";
    str +=
      n[5] != 0
        ? (str != "" ? " " : "") +
          (BnNumbers[Number(n[5])] || BnTens[n[5][0]] + " " + BnNumbers[n[5][1]]) +
          " টাকা "
        : "";
    return str + paisaInWord + "মাত্র।";
  }
```

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
