# JS Syntax

## let and const

Variables declared with let and const eliminate this specific issue of hoisting because they’re scoped to the block, not to the function. Previously, when you used var, variables were either scoped globally or locally to an entire function scope.

- Variables declared with let can be reassigned, but can’t be redeclared in the same scope. Use let when you plan to reassign new values to a variable.
- Variables declared with const must be assigned an initial value, but can’t be redeclared in the same scope, and can’t be reassigned. Use const when you don’t plan on reassigning new values to a variable.

---

## What about var

Is there any reason to use var anymore? Not really.

There are some arguments that can be made for using var in situations where you want to globally define variables, but this is often considered bad practice and should be avoided. From now on, we suggest ditching var in place of using let and const.

---

## Template Literals

Template literals are essentially string literals that include embedded expressions.

Denoted with backticks (``) instead of single quotes ( '' ) or double quotes ( "" ), template literals can contain placeholders which are represented using \${expression}. This makes it much easier to build strings.

---

## Destructuring

Destructuring borrows inspiration from languages like Perl and Python by allowing you to specify the elements you want to extract from an array or object on the left side of an assignment. It sounds a little weird, but you can actually achieve the same result as before, but with much less code; and it's still easy to understand.

When you destructure an object and store method into a variable, it no longer has access to "this" in the object which results may result in an error.

    const gemstone = {
        type: 'quartz',
        color: 'rose',
        carat: 21.29
    };
    const {type, color, carat} = gemstone;
    console.log(type, color, carat);

**_Eample_**

Destructuring Arrays:

    const things = ['red', 'basketball', 'paperclip', 'green', 'computer', 'earth', 'udacity', 'blue', 'dogs'];

    const [one , , , two, , , , three] = things;

    const colors = `List of Colors
    1. ${one}
    2. ${two}
    3. ${three}`;

    console.log(colors);

    Output:
    List of Colors
        1. red
        2. green
        3. blue

---

## Object literal shorthand & Shorthand method names

Instead of:

    let type = 'quartz';
    let color = 'rose';
    let carat = 21.29;

    const gemstone = {
        type: type,
        color: color,
        carat: carat
        calculateWorth: function() {
            // will calculate worth of gemstone based on type, color, and carat
        }
    };

Use

    let type = 'quartz';
    let color = 'rose';
    let carat = 21.29;

    const gemstone = {
        type,
        color,
        carat,
        calculateWorth(){ // the keyword function isn't needed
            // will calculate worth of gemstone based on type, color, and carat
        }
    };

## Loops

**for loop:** the biggest downside of a for loop is having to keep track of the counter and exit condition.

    const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
    for (let i = 0; i < digits.length; i++) {
        console.log(digits[i]);
    }

**for in:** improves upon the weaknesses of the for loop by eliminating the counting logic and exit condition. We still have to deal with the issue of using an index to access the values of the array, it almost makes it more confusing than before.

    const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
    for (const index in digits) {
        console.log(digits[index]);
    }

**For of loop:** improves upon the weaknesses of the for loop by eliminating the counting logic and exit condition. We still have to deal with the issue of using an index to access the values of the array, it almost makes it more confusing than before.

    const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
    for (const digit of digits) {
        console.log(digit);
    }

---

## Spread operator

The spread operator, written with three consecutive dots ( ... ), is new in ES6 and gives you the ability to expand, or spread, iterable objects into multiple elements.

**Eample 1:**

    const books = ["Don Quixote", "The Hobbit", "Alice in Wonderland", "Tale of Two Cities"];
    console.log(...books);

**Eample 2:**

    const fruits = ["apples", "bananas", "pears"];
    const vegetables = ["corn", "potatoes", "carrots"];
    const produce = [...fruits, ...vegetables];
    console.log(produce);

---

## Combining arrays with concat function

    const fruits = ["apples", "bananas", "pears"];
    const vegetables = ["corn", "potatoes", "carrots"];
    const produce = fruits.concat(vegetables);
    console.log(produce); // Prints: ["apples", "bananas", "pears", "corn", "potatoes", "carrots"]

---

## Rest parameter

The rest parameter, also written with three consecutive dots ( ... ), allows you to represent an indefinite number of elements as an array. This can be helpful in a couple of different situations.

    const order = [20.17, 18.67, 1.50, "cheese", "eggs", "milk", "bread"];
    const [total, subtotal, tax, ...items] = order;
    console.log(total, subtotal, tax, items);

**Variadic functions** is another use case for the rest parameter. Variadic functions are functions that take an indefinite number of arguments. This replaced the **arguments object**, _arguments_ is a keyword.

    function sum() {
        let total = 0;
        for (const argument of arguments) {
            total += argument;
        }
        return total;
    }

    let a = sum(12, 5, 6, 2, 7, 5, 1, 8, 1, 8, 1, 52, 9, 5, 1, );
    console.log(a);     // 123

This is misleading because we know the sum() function can handle an indefinite amount of arguments.
