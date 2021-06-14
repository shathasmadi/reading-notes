# Read: Class 03
## Passing Functions as Props

#### What does .map() return?
return new array with the same length of the original array with diffrent in values
#### If I want to loop through an array and display each value in JSX, how do I do that in React?
we loop through the numbers array using the JavaScript map() function. We return a li element for each item. Finally, we assign the resulting array of elements to listItems.

#### Each list item needs a unique key.

#### What is the purpose of a key?
A “key” is a special string attribute you need to include when creating lists of elements.
Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity
Keys used within arrays should be unique among their siblings. However, they don’t need to be globally unique. We can use the same keys when we produce two different arrays


#### What is the spread operator?
spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.
When ...arr is used in the function call, it ‘expands’ an iterable object arr into the list of arguments.

The Spread operator lets you expand an iterable like an object, string, or array into its elements while the Rest operator does the inverse by reducing a set of elements into one array

#### List 4 things that the spread operator can do.
1. Copying an array.
2. Concatenating or combining arrays.
3. Using Math functions.
4. Using an array as arguments.
5. Adding an item to a list.

#### Give an example of using the spread operator to combine two arrays.
const fewFruit = ['🍏','🍊','🍌']
const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]

#### Give an example of using the spread operator to add a new item to an array.
const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂

#### Give an example of using the spread operator to combine two objects into one.
const helloWorld = {…hello,…world} console.log(helloWorld) // Object { hello: “😋😛😜🤪😝”, world: “🙂🙃😉😊😇🥰😍🤩!” }

## Reesources:
[The Spread Operator](https://reactjs.org/docs/lists-and-keys.html)

[How to Pass Functions Between Components](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)

[React Tutorial through ‘Declaring a Winner’](https://reactjs.org/tutorial/tutorial.html)

[React Docs - Lifting State Up](https://reactjs.org/tutorial/tutorial.html)