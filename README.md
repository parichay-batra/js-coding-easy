# Given two arrays, find the intersection(items occur in both arrays)
arrays are not sorted, and might have duplicates.
you can modify the arrays
you can return the items in any order, but without duplicates.


# Given an array of integers, all integers appear twice except one integer, could you quickly target it ?
const arr = [10, 2, 2 , 1, 0, 0, 10]
findSingle(arr) // 1

What is time & space cost of your approach ? Could you do better ?
# Please create a function count(), when called it should return how many times it has been called, count.reset() should also implemented.
count() // 1
count() // 2
count() // 3

count.reset()

count() // 1
count() // 2
count() // 3

# Let's do some simple two-way binding.

Please create a function model(state, element), to bind state.value to the HTMLInputElement element.

const input = document.createElement('input')
const state = { value: 'Himanshi' }
model(state, input)

console.log(input.value) // 'Parichay '
state.value = 'dev'
console.log(input.value) // 'Batra'
input.value = 'BFE.dev'
input.dispatchEvent(new Event('change'))
console.log(state.value) // 'Parichat Batra'

# Create an object with property count, which increments every time count is accessed, initial value is 0.

const counter = createCounter()
counter.count // 0, then it should increment
counter.count // 1
counter.count // 2
counter.count = 100 // it cannot be altered
counter.count // 3

# Given a non-empty string, return the most frequently ocurring character.

If there are multiple characters with same occurrance, return an array of them.

count('abbccc')
// 'c'
count('abbcccddd')
Follow-up: What is the time & space complexity of your approach?

# Object.is() is similar to === except following cases

Object.is(0, -0) // false
0 === -0 // true
Object.is(NaN, NaN) // true
NaN === NaN // false
Here is the detailed spec, can you implement your own is()?

# Given an array of numbers, pick any two numbers a and b, we could get the difference by Math.abs(a - b).

Can you write a function to get the largest difference?

largestDiff([-1, 2,3,10, 9])
// 11,  obviously Math.abs(-1 - 10) is the largest
largestDiff([])
// 0
largestDiff([1])
// 0

# Given an array of integers, find two number that sums up to 0, return their indices.

There might be multiple pairs, any of them would do. If not found, return null

findTwo([1,2,3,-1])
findTwo([1,2,3,-1,-2,0])
findTwo([1,2,3,4])
// null

# Given a string which might have duplicate letters, write a function to find the first duplicate.

firstDuplicate('abca')
// 'a'
firstDuplicate('abcdefe')
// 'e'
firstDuplicate('abcdef')
// null
What is the time & space cost of your approach ? Can you do better?

# There is already Array.prototype.flat() in JavaScript (ES2019), which reduces the nesting of Array.

Could you manage to implement your own one?

Here is an example to illustrate

const arr = [1, [2], [3, [4]]];
flat(arr)
flat(arr, 1)
flat(arr, 2)
follow up

Are you able to solve it both recursively and iteratively?

# Given a string contaning only a, b and c, remove all b and ac.

removeChars('ab') // 'a'
removeChars('abc') // ''
removeChars('cabbaabcca') // 'caa'
What is the time and space complexity of your approach?

# Here is a sequence:

'1', first number is 1
'11', since previous number has One(1) 1
'21', since previous number has Two(2) 1s
'1211', since previous number has One(1) 2 and One(1) 1
'111221', since previous number has One(1) 1, One(1) 2, Two(2) 1s
'312211', since previous number has Three(3) 1s, Two(2) 2s, One(1) 1
....
As explained above, the sequence is generated by counting the digits of previous number.

Please create getNthNum(n) to return the n-th number string in the sequence, n starts from 1.

# Let's take a look at following error-first callback.

```const callback = (error, data) => {
  if (error) {
    // handle the error
  } else {
    // handle the data
  }
}```

Now think about async functions that takes above error-first callback as last argument.

```
const func = (arg1, arg2, callback) => {
  // some async logic
  if (hasError) {
    callback(someError)
  } else {
    callback(null, someData)
  }
}
```
You see what needs to be done now. Please implement promisify() to make the code better.
  ```
const promisedFunc = promisify(func)
promisedFunc().then((data) => {
  // handles data
}).catch((error) => {
  // handles error
})

```

# Debounce is a common technique used in Web Application, in most cases using lodash solution would be a good choice.

could you implement your own version of basic debounce()?

In case you forgot, debounce(func, delay) will returned a debounced function, which delays the invoke.

Here is an example.

Before debouncing we have a series of calling like

─ A ─ B ─ C ─ ─ D ─ ─ ─ ─ ─ ─ E ─ ─ F ─ G 
After debouncing at wait time of 3 dashes

─ ─ ─ ─ ─ ─ ─ ─ D ─ ─ ─ ─ ─ ─ ─ ─ ─ G 

# what is Composition? It is actually not that difficult to understand, see @dan_abramov 's explanation.

Here you are asked to create a pipe() function, which chains multiple functions together to create a new function.

Suppose we have some simple functions like this

const times = (y) =>  (x) => x * y
const plus = (y) => (x) => x + y
const subtract = (y) =>  (x) => x - y
const divide = (y) => (x) => x / y
Your pipe() would be used to generate new functions

pipe([
  times(2),
  times(3)
])  
// x * 2 * 3
pipe([
  times(2),
  plus(3),
  times(4)
]) 
// (x * 2 + 3) * 4
pipe([
  times(2),
  subtract(3),
  divide(4)
]) 
// (x * 2 - 3) / 4
notes

to make things simple, functions passed to pipe() will all accept 1 argument

# Currying is a useful technique used in JavaScript applications.

Please implement a curry() function, which accepts a function and return a curried one.

Here is an example

const join = (a, b, c) => {
   return `${a}_${b}_${c}`
}
const curriedJoin = curry(join)
curriedJoin(1, 2, 3) // '1_2_3'
curriedJoin(1)(2, 3) // '1_2_3'
curriedJoin(1, 2)(3) // '1_2_3'
more to read

https://javascript.info/currying-partials

https://lodash.com/docs/4.17.15#curry

# 
// Given an input of array, 
// which is made of items with >= 3 properties
let items = [
  {color: 'red', type: 'tv', age: 18}, 
  {color: 'silver', type: 'phone', age: 20},
  {color: 'blue', type: 'book', age: 17}
] 
// an exclude array made of key value pair
const excludes = [ 
  {k: 'color', v: 'silver'}, 
  {k: 'type', v: 'tv'}, 
  ...
] 
function excludeItems(items, excludes) { 
  excludes.forEach( pair => { 
    items = items.filter(item => item[pair.k] === item[pair.v])
  })
 
  return items
} 
What does this function excludeItems do?
Is this function working as expected ?
What is the time complexity of this function?
How would you optimize it ?

# Suppose we have an array of items - A, and another array of indexes in numbers - B

const A = ['A', 'B', 'C', 'D', 'E', 'F']
const B = [1,   5,   4,   3,   2,   0]
You need to reorder A, so that the A[i] is put at index of B[i], which means B is the new index for each item of A.

For above example A should be modified inline to following

['F', 'A', 'E', 'D', 'C', 'B']
The input are always valid.

follow-up

It is fairly easy to do this by using extra O(n) space, could you solve it with O(1) space?

# Can you create a range(from, to) which makes following work?

for (let num of range(1, 4)) {
  console.log(num)  
}
// 1
// 2
// 3
// 4
This is a simple one, could you think more fancy approaches other than for-loop?

Notice that you are not required to return an array, but something iterable would be fine.

# _.once(func) is used to force a function to be called only once, later calls only returns the result of first call.

Can you implement your own once()?

function func(num) {
  return num
}
const onced = once(func)
onced(1) 
// 1, func called with 1
onced(2)
// 1, even 2 is passed, previous result is returned 

# Memoization is a common technique to boost performance. If you use React, you definitely have used React.memo before.

Memoization is also commonly used in algorithm problem, when you have a recursion solution, in most cases, you can improve it by memoization, and then you might be able to get a Dynamic Programming approach.

So could you implement a general memo() function, which caches the result once called, so when same arguments are passed in, the result will be returned right away.

const func = (arg1, arg2) => {
  return arg1 + arg2
}
const memoed = memo(func)
memoed(1, 2) 
// 3, func is called
memoed(1, 2) 
// 3 is returned right away without calling func
memoed(1, 3)
// 4, new arguments, so func is called
The arguments are arbitrary, so memo should accept an extra resolver parameter, which is used to generate the cache key, like what _.memoize() does.

const memoed = memo(func, () => 'samekey')
memoed(1, 2) 
// 3, func is called, 3 is cached with key 'samekey'
memoed(1, 2) 
// 3, since key is the same, 3 is returned without calling func
memoed(1, 3) 
// 3, since key is the same, 3 is returned without calling func
Default cache key could be just Array.from(arguments).join('_')

note

It is a trade-off of space for time, so if you use this in an interview, please do analyze how much space it might cost.

# You are asked to reverse a linked list.

Suppose we have Node interface like this

class Node {
   new(val: number, next: Node);
   val: number
   next: Node
}
We can then chain nodes together to create a linked list.

const Three = new Node(3, null)
const Two = new Node(2, Three)
const One = new Node(1, Two)
//now we have  a linked list
// 1 → 2 → 3
Now how can you reverse it to 3 → 2 → 1 ? you can modify the next property of each node, but not the val.

Follow up

Could you solve it with and without recursion?

# 
