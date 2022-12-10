# JavaScript Task 

![](https://img.shields.io/static/v1?label=HTML&message=v.5&color=red)
![](https://img.shields.io/static/v1?label=CSS&message=v.3&color=blue)
![](https://img.shields.io/static/v1?label=SCSS&message=v.1.56&color=blue)
![](https://img.shields.io/static/v1?label=JavaScript&message=v.1.56&color=yellow)


## Table of content

- [Technologies](#technologies)
- [Requirements](#requirements)
- [Project structure](#project-structure)
- [Getting started](#getting-started)

## Technologies

- HTML
- SCSS/SASS for styling
    - Variable
    Mixin
    Extend
- CSS
    - Flex and Grid system
- JavaScript

## Requirements

- Var and it’s problems
- Let and why It’s better,
- Import of const
- Class and contruction
- Class inheritance
- Higher-order functions 
- Methods
- Closures
- fetching data



## Project structure

```shell
.
├── README.md
├── img
│   ├── Task4.png
│   └── Task4B.png
├── index.html
├── index.js

├── package-lock.json
├── package.json
└── src
    ├── css
    │   ├── styles.css
    │   └── styles.css.map
    └── scss
        ├── features
        │   ├── _button.scss
        │   ├── _card.scss
        │   └── _input.scss
        └── styles.scss
```

## Getting started

- The fourth task is based on the method in javascript and how to fetch data from REST API.

![Task](/img/Task4.png)

- Users can search for any country by typing the name of the desired country and clicking on get country. The result will display under the search input menu.

![Task4B](/img/Task4B.png)

- The sixth task is based on the class inheritance function, in which one class extends into another by creating new functionality on top of the existing class.

```js
class Book {
    _title
    constructor(title, cost, profit) {
        if (cost <= 0) {
            throw new Error("cost less than zero");
        }
        if (profit <= 0 || profit >= 0.5) {
            throw new Error("positive number > 0 and =< 0.5 is required");
        }
        if (title && title.length < 1) {
            throw new Error("title shouldnot be empty");
        }
     
        this._title = title;
        this.cost = cost;
        this.profit = profit;
    }
    
    bookPrice() {
        return this.cost/( 1- this.profit)
    };

    bookProfit() {
        return this.bookPrice() * this.profit;
    };

    priceIncrement () { 
        return this.bookPrice() + 1;
    };

    priceDecrement () { 
        return this.bookPrice() - 1;
    }

}

class TaxableBook extends Book{
    /* provide your code here */
    constructor(title, cost, profit, taxRate) {
        super(title, cost, profit);
        this.taxRate = taxRate;
    };

    priceWithTaxRate() {
        return this.cost / (1 - this.profit - this.taxRate / 100);
    }
}

const book1 = new Book("The Power of Habits", 14, 0.3)
const book2 = new TaxableBook("The Power of Habits", 14, 0.3, 24)

console.log(book1.bookPrice())
console.log(book2.bookPrice())

console.log(book1.bookProfit())
console.log(book2.bookProfit())

console.log(book2.priceWithTaxRate().toFixed(2))
```
