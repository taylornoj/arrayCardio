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

3. Sort the inventors by birth year, oldest to youngest:
```javascript
const ordered = inventors.sort((a, b) => a.year > b.year ? 1 : -1);
```
![oldest to youngest](https://github.com/taylornoj/arrayCardio/blob/master/docs/birthyearSort.jpg?raw=true)

4. Add up the years lived, of all inventors:
```javascript
const totalYears = inventors.reduce((sum, inventor) => {
      return sum + (inventor.passed - inventor.year);
    }, 0);
```
![total years lived](https://github.com/taylornoj/arrayCardio/blob/master/docs/totalYearsLived.jpg?raw=true)

5. Sort the inventors by years lived:
```javascript
const oldest = inventors.sort(function (a, b) {
      const olderPerson = a.passed - a.year;
      const youngerPerson = b.passed - b.year;
      return olderPerson > youngerPerson ? -1 : 1;
    });
```
![years lived](https://github.com/taylornoj/arrayCardio/blob/master/docs/oldestToYoungest.jpg?raw=true)

6. Work was done on dev tools via Wikipedia page

7. Sort list of people alphabetically by last name:
My solution:
```javascript
const lastName = people.sort();
    console.log(lastName);
```

Wes' solution:
```javascript
const alpha = people.sort((lastOne, nextOne) => {
      const [aLast, aFirst] = lastOne.split(', ');
      const [bLast, bFirst] = nextOne.split(', ');
      return aLast > bLast ? 1 : -1;
    });
```
![alpha sort](https://github.com/taylornoj/arrayCardio/blob/master/docs/sortAlpha.png?raw=true)

8. Sum up the instances of each:
```javascript
const transportation = data.reduce(function (obj, item) {
      if (!obj[item]) { 
        obj[item] = 0;  
      }
      obj[item]++; 
      return obj;

    }, {}); 
```
![sum all transpo](https://github.com/taylornoj/arrayCardio/blob/master/docs/reduce.jpg?raw=true)