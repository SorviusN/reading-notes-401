# Spread Operator

## 3 places to use spread.
1. In function calls
``` js
let str = "BANANAS";

console.log(...str);
// This will log every single character individually within bananas.
// Same thing can be done for other types.

// You may call a Divide function with a bunch of different numbers in an array.

const divide = (num) => {
    let a = num / 2;
    return a;
}

let nums = [1, 2, 3, 4, 5];
let arrOfDividends = divide(...nums);

// arr of dividends will be 1/2, 2/2, 3/2, 4/2 and so on.

```
2. In array literals 
``` js
// you can use this day to day.

const parents = ['Lorrie', 'Steve'];
const kids = ['Jake','Annie'];

const fullFam = [...kids, ...parents, "Myself"];

// makes one array from both of the previous arrays.

// You may also create copies of an array with the spread operator. Any type of array.
```

3. In object literals


 https://www.youtube.com/watch?v=pYI-UuZVtHI