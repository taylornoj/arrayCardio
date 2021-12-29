# Array Cardio

This work from day 4/30 of the [JavaScript 30 challenge](https://github.com/wesbos/JavaScript30).

This challenge is not about creating an app - it's about practicing JavaScripts most prominent array functions (.filter(), .map(), .reduce() and .sort()).

The starter file contained arrays with data to do some Array Cardio!

Although the objective is to display the results in Chrome Dev Tools from the browser, I found that with one function in particular, the resulting array would alter after an additional sort function was added later in the code.  For this reason I will be posting the results below, rather than linking to a browser until I can find the source of the issue.

## What I learned:
- learned about console.table which displays data is an organized way
- we had previously learned about NodeList - now we reversed the logic using Array.from to apply array methods to a NodeList

## The Cardio

1. Filter the list of inventors for those who were born in the 1500's:
```javascript
  const fifteen = inventors.filter(inventor => {
      if (inventor.year >= 1500 && inventor.year < 1600) {
        return true;
      }
    });
```
![lived in 1500's](https://github.com/taylornoj/arrayCardio/blob/master/docs/livedIn1500.jpg?raw=true)


2. Create an array of the inventors first and last names:
```javascript
const inventorNames = inventors.map(inventor =>
      `${inventor.first} ${inventor.last}`);
```
![inventors names](https://github.com/taylornoj/arrayCardio/blob/master/docs/firstLastNames.jpg?raw=true)
