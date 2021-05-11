# Array Methods

# map()

### Description of what method does:

applies a function on every element in an array. A new array is then returned

### How it works:

### Syntax:

```jsx
array.map(function(currentValue, index, arr), thisValue)

let newArr = oldArr.map((val, index, arr) => {
	//return element to new Array
})
```

### Example 1:

multiply each number in array by a given integer

```jsx
const sweetArray = [2, 3, 4, 5, 35]
const sweeterArray = sweetArray.map(sweetItem => {
    return sweetItem * 2
})

console.log(sweeterArray)//[ 4, 6, 8, 10, 70 ]
```

### Example 2:

return an object with the value and index of each element in the array

```jsx
arr = [1,2,3,4];

let newArr = arr.map((val, i, arr) => {  return {
    value: val,
    index: i
  };});

newArr = [
  {value: 1, index: 0},
  {value: 2, index: 1},
  {value: 3, index: 2},
  {value: 4, index: 3}
]
```

### Example 3:

double the even numbers and leave the odd numbers the same

```jsx
let arr = [1,2,3,4];

let newArr = arr.map((v,i,a) => {
  return v % 2 === 0 ? v * 2 : v;
});
// newArr = [1,4,3,8];
```

# reduce()

### Description of what method does:

used to apply a function to each element in the array to reduce the array to a single value

### How it works:

### Syntax:

```jsx
let result = arr.reduce(callback);
// Optionally, you can specify an initial value
let result = arr.reduce(callback, initValue);
```

### Example 1:

find the sum of all the values of an array

```jsx
let arr = [1,2,3,4];
let sum = arr.reduce((acc, val) => {
  return acc + val;
});
sum = 10
```

### Example 2:

sum up the population of every country except China

```jsx
let data = [
  {
    country: 'China',
    pop: 1409517397,
  },
  {
    country: 'India',
    pop: 1339180127,
  },
  {
    country: 'USA',
    pop: 324459463,
  },
  {
    country: 'Indonesia',
    pop: 263991379,
  }
]

let sum = data.reduce((acc, val) => {
  return val.country == 'China' ? acc : acc + val.pop;
}, 0);

sum = 1927630969
```

### Example 3:

## filter()

### Description of what method does:

returns a new array created from all elements that pass a certain test preformed on an original array

### How it works:

### Syntax:

```jsx
let newArr = oldArr.filter(callback);
```

### Example 1:

filter out all the even numbers from the array

```jsx
let arr = [1,2,3,4,5,6]

let filtered = arr.filter( val => {
    return val % 2 === 1
})

//filtered = [2,4,6]
```

### Example 2:

create a new array with only the countries that have a population higher than 500 million.

```jsx
let data = [
    {
      country: 'China',
      population: 1409517397,
    },
    {
      country: 'India',
      population: 1339180127,
    },
    {
      country: 'USA',
      population: 324459463,
    },
    {
      country: 'Indonesia',
      population: 263991379,
    }
  ]

let highPopulation = data.filter( val => {
      return val.population > 500000000
  })

// cities = [{country: "China", population: 1409517397},
             {country: "India", population: 1339180127}]
```

### Example 3:

Create an array of student ages that meet the legal drinking age

```jsx
const studentsAge = [17, 16, 18, 19, 21, 17];
const ableToDrink = studentsAge.filter( age => age > 18 );
// ableToDrink will be equal to [19, 21]
```

## forEach()

### Description of what method does:

executes a function on each element in an array

loops through an array

### How it works:

passes a [callback function](https://www.freecodecamp.org/news/javascript-callback-functions-what-are-callbacks-in-js-and-how-to-use-them/) for each element of an array together with the following parameters:

- Current Value (required) - The value of the current array element
- Index (optional) - The current element's index number
- Array (optional) - The array object to which the current element belongs

### Example 1:

Get the sum of all the values in the array:

```jsx
var sum = 0;
var numbers = [65, 44, 12, 4];
numbers.forEach(myFunction);

function myFunction(item) {
  sum += item;
  document.getElementById("demo").innerHTML = sum;
}
```

### Example 2:

For each element in the array: update the value with 10 times the original value:

```jsx
var numbers = [65, 44, 12, 4];
numbers.forEach(myFunction)

function myFunction(item, index, arr) {
  arr[index] = item * 10;
}
```

### Example 3:

## sort()

### Description of what method does:

sorts the elements of an array and returns the new sorted array.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## slice()

### Description of what method does:

slice method can takes two arguments, first is start index and second is end index and returns an array that has only the elements between those two indexes. The start index is required, the end index optional, if end index is not given then extract till end of the array.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## pop()

### Description of what method does:

pop method removes the last element from an array and returns that removed element.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## shift()

### Description of what method does:

similar to pop method, shift removes the first element from an array and returns that element.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## push()

### Description of what method does:

push adds one or more elements to the end of an array and returns the updated length of array.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## unshift()

### Description of what method does:

similar to push method, unshift method add one or more elements to the front of an array and returns the updated length of the array.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## includes()

### Description of what method does:

return true or false whether an array contains a certain element, which is passed as an argument in the includes function.

### How it works:

### Example 1:

Check if the array includes an item with the string ‘waldo’.

```jsx
const names = ['sophie', 'george', 'waldo', 'stephen', 'henry'];
const includesWaldo = names.includes('waldo');
// includesWaldo will be equal to true
```

### Example 2:

### Example 3:

## indexOf()

### Description of what method does:

Returns the index of first (least) occurrence of element within the array which is given, or -1 if none is found. It also take second argument which is optional and specify from where to start.

### How it works:

### Example 1:

### Example 2:

### Example 3:

## every()

### Description of what method does:

checks if all items in an array pass a condition

### How it works:

### Example 1:

Check if all ratings are equal to or greater than 3 stars

```jsx
const ratings = [3, 5, 4, 3, 5];
const goodOverallRating = ratings.every( rating => rating >= 3 );
// goodOverallRating will be equal to true
```

### Example 2:

### Example 3:
