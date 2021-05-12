# Array Methods

Describe the map() array method and give an example when to use it

# map()

### Description of what method does:

applies a function on every element in an array. A new array is then returned

### How it works:

- Takes a callback function that is called once for each element.
- Calls the callback function and gets the result of the operation run on the element
- Returns a new array with the results> The .map() method creates a new array and doesn't mutate the old array.

### Syntax:

```jsx
array.map(function(currentValue, index, arr), thisValue)

let newArr = oldArr.map((val, index, arr) => {
	//return element to new Array
})
```

### Time Complexity:

0(n)

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

### Time Complexity:

0(n)

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

- Will take a test function
- Returns a new array containing the elements that matches the set test
- Returns an empty array if there are no matches

### Syntax:

```jsx
let newArr = oldArr.filter(callback);
```

### Time Complexity:

0(n)

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

### Time Complexity:

0(n)

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

### Time Complexity:

0(n log(n))

### Example 1:

sort in alphabetical order in ascending order

```jsx
let animals = [
    'cat', 'dog', 'elephant', 'bee', 'ant'
];
animals.sort();

console.log(animals);//[ 'ant', 'bee', 'cat', 'dog', 'elephant' ]
```

### Example 2:

sort in alphabetical order in descending order

```jsx
let animals = [
    'cat', 'dog', 'elephant', 'bee', 'ant'
];
animals.sort((a,b) => b - a);

console.log(animals)// [ 'elephant', 'dog', 'cat', 'bee', 'ant' ]
```

### Example 3:

## slice()

### Description of what method does:

slice method can takes two arguments, first is start index and second is end index and returns an array that has only the elements between those two indexes. The start index is required, the end index optional, if end index is not given then extract till end of the array.

### How it works:

### Syntax:

```jsx
array.slice(start, end)
```

### Time Complexity:

0(n)

### Example 1:

get the last two users of the array

```jsx
//  An array of objects
const users = [{name: 'Pete', id: 1}, {name: 'Rich', id: 2}, {name: 'Johnny', id: 3}];

// Copy users from a particular index
const lastUsers = users.slice(1);

// Output users from the selected range
console.log(lastUsers);

//output: [{"name":"Rich","id":2},{"name":"Johnny","id":3}]
```

### Example 2:

return an array of 4 and 5

```jsx
const numbers = [2, 3, 4, 5, 6];
const sliced = numbers.slice(2,4);
console.log(sliced);

//output: Array [4,5]
```

### Example 3:

## pop()

### Description of what method does:

pop method removes the last element from an array and returns that removed element.

### How it works:

- Removes the element at the last index of the array.
- Mutates the parent array reducing the length.
- Returns the last element.

### Syntax:

```jsx
array.pop()
```

### Time Complexity:

0(1)

### Example 1:

remove an item in a list and return the list

```jsx
let items = ['Cedar', 'Fruits', 'Table'];

// Remove last item in list
let newItems = items.pop();

// Output modified list
console.log(items);

// Output removed item
console.log(newItems)

//output: ["Cedar","Fruits"]
//output: Table
```

### Example 2:

### Example 3:

## shift()

### Description of what method does:

This method takes out the first element from an array and returns it. The shift method mutates the array during this process, reducing its length.

### How it works:

- Removes the element at the beginning of the array.
- Mutates the parent array reducing the length.
- Returns the removed element

### Syntax:

```jsx
array.shift()
```

### Time Complexity:

0(n)

### Example 1:

remove the first number in the list

```jsx
// List of numbers
const list = [10, 20, 30, 40, 50]

// Remove first number
const newList = list.shift()

// Output result
console.log(newList)

//output: 10
```

### Example 2:

remove the index element from an array

```jsx
// New array
const numbers = ['ten', 'one', 'two', 'three', 'four'];

// Remove the first element
numbers.shift();

// Output result
console.log(numbers);

//output: ["one","two","three","four"]
```

### Example 3:

## push()

### Description of what method does:

This methods adds one or more value to the last position of an array. This method mutates the array returning the new length of the array.

### How it works:

- Takes a value or values as arguments.
- Adds the value(s) to the end of the array.
- Returns the new length of the array.

### Syntax:

```jsx
array.push(element)
```

### Time Complexity:

0(1)

### Example 1:

add a new value to the end of the array

```jsx
// List of numbers
const numbers = [1, 2, 3, 4, 5];

// Add a number to the end
numbers.push(6);

// Output result
console.log(numbers);//[1,2,3,4,5,6]
```

### Example 2:

add a new item to todo list

```jsx
// List of todos
const todos = [{name: 'Clean room', complete: false}];

// Add todo item
todos.push({name: 'Cook food', complete: true})

// Output updated todo list
console.log(todos)//[{"name":"Clean room","complete":false},{"name":"Cook food","complete":true}]
```

### Example 3:

## unshift()

### Description of what method does:

similar to push method, unshift method add one or more elements to the front of an array and returns the updated length of the array.

### How it works:

### Syntax:

```jsx
const newArray = oldArray.unshift(item1, item2, ...itemN)
```

### Time Complexity:

0(n)

### Example 1:

add new items to the the beginning of the array

```jsx
// Array of items
const items = ['Cedar', 'Fruits', 'Table'];

// Add new items to array
items.unshift('wine', 'glass');

// Display modified array
console.log(items);//["wine","glass","Cedar","Fruits","Table"]
```

### Example 2:

add items to cart

```jsx
// Array of objects in cart
const cart = [
  {
    item: "bread",
    price: 2000,
  },
  {
    item:"milk",
    price: 1000
  }
]

// Add item to cart
cart.unshift({item: "eggs", price: 500})

// Display modified array
console.log(cart)//[{"item":"eggs","price":500},{"item":"bread","price":2000},{"item":"milk","price":1000}]
```

### Example 3:

## includes()

### Description of what method does:

return true or false whether an array contains a certain element, which is passed as an argument in the includes function.

### How it works:

- Takes a value as an argument
- Checks the array if the value exists within the array
- Returns `true` or `false`.
- If no argument is provided, it returns `false`.

### Syntax:

```jsx
array.includes(searchValue, startIndex)
```

### Time Complexity:

0(n)

### Example 1:

Check if the array includes an item with the string ‘waldo’.

```jsx
const names = ['sophie', 'george', 'waldo', 'stephen', 'henry'];
const includesWaldo = names.includes('waldo');
// includesWaldo will be equal to true
```

### Example 2:

Check if the array contains a certain month

```jsx
// Weekdays
const days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'];

// Random month
const month = 'May';

// Verify inclusion in array
const isDay = days.includes(month);

// Output result
console.log(isDay);
```

### Example 3:

## indexOf()

### Description of what method does:

Returns the index of first (least) occurrence of element within the array which is given, or -1 if none is found. It also take second argument which is optional and specify from where to start.

### How it works:

### Time Complexity:

0(n)

### Example 1:

locate the values of a give value

```jsx
var array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0
```

### Example 2:

find all the occurrences of an element

```jsx
var indices = [];
var array = ['a', 'b', 'a', 'c', 'a', 'd'];
var element = 'a';
var idx = array.indexOf(element);
while (idx != -1) {
  indices.push(idx);
  idx = array.indexOf(element, idx + 1);
}
console.log(indices);
// [0, 2, 4]
```

### Example 3:

find if an element exists in the array or not and update the array

```jsx
function updateVegetablesCollection (veggies, veggie) {
    if (veggies.indexOf(veggie) === -1) {
        veggies.push(veggie);
        console.log('New veggies collection is : ' + veggies);
    } else if (veggies.indexOf(veggie) > -1) {
        console.log(veggie + ' already exists in the veggies collection.');
    }
}

var veggies = ['potato', 'tomato', 'chillies', 'green-pepper'];

updateVegetablesCollection(veggies, 'spinach');
// New veggies collection is : potato,tomato,chillies,green-pepper,spinach
updateVegetablesCollection(veggies, 'spinach');
// spinach already exists in the veggies collection.;
```

## every()

### Description of what method does:

The every method checks that each element in an array passes a set test. This method will return true if all the elements pass the set. Once an element that fails the test is found, the method returns false.

### How it works:

- Takes a callback function that implements a test
- Checks if all the elements pass the test
- Returns `true` if `every` element passes the test.
- Returns `false` an element fails test

### Syntax:

```jsx
const isCorrect = array.every(callback[,thisArg])
```

### Time Complexity:

0(n)

### Example 1:

Check if all ratings are equal to or greater than 3 stars

```jsx
const ratings = [3, 5, 4, 3, 5];
const goodOverallRating = ratings.every( rating => rating >= 3 );
// goodOverallRating will be equal to true
```

### Example 2:

compare two arrays

```jsx
function arraysEqual(arr1, arr2) {
  return arr1.length === arr2.length && arr1.every((value, index) => value === arr2[index]);
}

alert( arraysEqual([1, 2], [1, 2])); // true
```

### Example 3:

test all items in an array of objects using either the object keys

```jsx
// Array of students
const students = [{name: 'John', score: 50} , {name: 'Peter', score: 60}, {name: 'James', score: 55}];

// Threshold Score
const passScore = 50;

// Test students
const studentsPassed = students.every(student => student.score >= passScore);

// Display status
console.log(studentsPassed)//true
```
