Javascript Topics:

- primitives data types
- variables, string, numbers, booleans, undefined, null, NaN
- arithmetic operators
- comparison operators
- logical operators
- conditional statements (if else, switch)
- functions, arguments, return statement, scope
- callbacks, higher order functions
- for loops, while, do while
- Arrays
    - declaration
    - accessing items
    - assignment
    - Array methods
    - 2D array
    - 3D array
    - forEach, map, reduce, filter callbacks
- Objects
    - difference from arrays
    - key value pair
    - accessing values
    - assigning values
    - methods
    - for in loop
    - this
- hoisting

Examples of Above topics related:
```js
// undefined == null
// undefined === null
// NaN == NaN
// [] == []
// console.log({1:'name'} === {1:'name'})

// arithmetic operators
// conditional operators in react { data && data.item && data.item.map }
// 5 && 2 && 0 || 2 && 3 || 15 && 21
// 5 && 2 && 0 || 2 == 3 || 15 && 21
// 5 && 2 && 0 || 2 == 3
// precedence

// map, forEach, filter, reduce


// var arr = [1,2,3,4]

// newArr = arr.filter((a,i)=>a>2)

// var arr = new Array(1,2,3)
// console.log(arr)
// index value
// console.log(typeof arr === typeof {})

// 2d arrays, mxn

// transpose of an array. MxN -> NxM

// var key = '1'
// var key2 = '2'

// var obj = {
//   1: 'value',
//   2: 'value2'
// }

// obj[key]


// for(let key in obj){
//   console.log(key, obj[key])
// }

// hoisting
// var x = 100

// function test(){
// //   right to left
//   console.log('value',x)
// //   100, 10
//   var i = 10,
//           x = i

// }
// test()
// console.log(x)

// 100,undefined
// Ref

// var, let, const


// redeclaration let x = 10   ... let x = 20
// let x = 100
// let x =20

const name = [1,2,3]

name[1] = 4
name
```
- scopes
    - global
    - local scope
    - block scope
- closures
- lexical scoping
- Execution context
- strict mode
- solve problems faster by using objects 
- recursion

Examples of Above topics related:
```js
// var arr = [1,2,3,4,5]

// for(var i=0; i<arr.length; i++){
//   setTimeout(()=>console.log(arr[i],i),i*1000)
// }

// console.log('value of i after for loop',i)

// expected
// 1 0
// 2 1
// 3 2
// 4 3
// 5 4

// value is 
// undefined 5 -> 5 times -> 1 sec intervals

// IIFE

// for(var i=0; i<arr.length; i++){
//   setTimeout(function(i){
//        return function(){
//       console.log(arr[i],i)
//     } 
//   }(i),i*1000)
// }

// function display(i){
//   setTimeout(()=>console.log(this[i],i),i*1000)
// }


// for(var i=0; i<arr.length; i++){
//   display.call(arr,i)
// }


// for(let i=0; i<arr.length; i++){
//     //   locally scoped
//   setTimeout(()=>console.log(arr[i],i),i*1000)
// }

// // closures, scopes, eventloop, call,apply,bind/functions

Extra questions on closures:

write function for sum(5)(10)(2)

What is debouncing? Write a function to explain debouncing? 

// DE-BOUNCING: EXTRA

// minimise the no api requsest
// 

const debounce = (func, delay) => {
    // if the request or call is not interrupted for delay milliseconds
    // then the function should be fired
    let debouncing
    return function(){
        clearTimeout(debouncing)
        debouncing = setTimeout(()=>func.apply(this,arguments), delay )
    }
}


// 'use strict'

// function test(){
//     console.log(this)
// }

// test()


// 'key,value,pair,javascript'
// {key:{value:{pair:{javascript:{}}}}}

// for loop

// var str = 'key,value,pair,javascript'

// var arr = str.split(',')

// var obj = {}
// obj[arr[arr.length-1]] = {}
// for(var i=arr.length-2;i>=0; i--){
//     obj[arr[i]] = {...obj}

//     delete obj[arr[i+1]]
// }

// console.log(obj)

// 'key,value,pair,javascript'
// {key:{value:{pair:{javascript:{}}}}}

// // for loop

// var str = 'key,value,pair,javascript'

// var arr = str.split(',')

// var rec = (arr,i=0,obj={}) => {
//   if(i===arr.length){
//     return obj
//   }
//   else{
//       obj[arr[i]] = rec( arr, i+1 )
//       return obj
//   }
// }

// // recursion
// var str = 'key,value,pair,javascript'

// var arr = str.split(',')

// var obj = {}

// // recursion

// var rec =( arr , i=0 , obj={}) => !arr[i] ? obj : { [arr[i]]: rec(arr,i+1) } 

// console.log( rec(arr) )
```

- DOM manipulation 
    - createElement
    - append
    - getElementById
    - querySelector
    - querySelectorAll
    - setAttribute
    - children methods
- event API, eventListener
- event bubbling
- event capturing
- style and attribute manipulation with DOM
- JSON
- using AJAX / XHR
- callback, callback hell
- asyncrnonous behavior in javascript
    - setTimeout
    - setInterval
- event loop
    - call stack
    - task/event queue
- WEB API
- promises
    - promise chaining
    - advantage over callbacks
- async, await
- fetch API
- axios

Examples of Above Topics Related:
```js
// promises
// what
// why
// how

// 3 states
// fulfilled, rejected, pending
// sleep(2000)
// .then(operation1)
// .then(operation2)
// .then(operation3)
// .catch(operation3)
// .finally(operation3)

function sleep(time){
    return new Promise((res,rej)=>{
        if(typeof time !== 'number'){
            rej('argument to sleep function should be a number')
            return
        }
        setTimeout(() => {
            res({status:200})
        }, time);
    })
}

// setTimeout(() => {
//     console.log('first')
// }, 0    );

// Promise.resolve()
// .then(res=>console.log('promise'))

// sleep(1000)
// .then(res=>console.log('printed after 2s'))
// .catch(err=>console.log(err))

// async function test(){
//     try{
//         console.log('waiting for results')
//         let res = await sleep(2000)

//         console.log(res)
//         if(res.status===200){
//             return true
//         }
//     }
//     catch(err){
//         console.log(err)
//     }
// }

// test()
// .then(res=>{
//     console.log(res)
// })

var promise = []
promise[0] = sleep(100).then(res=>'promise 1')
promise[1] = sleep(500).then(res=>{
    throw new Error('error message')
}).catch(err=>err)
promise[2] = sleep(2000).then(res=>'promise 3')
promise[3] = sleep(1000).then(res=>'promise 4')

Promise.all( promise ).then(res=>console.log(res))


parallel requests. 20 req. 
Promises.all( promise1, promise2 ).then(res=>console.log(res))


waterfall model. 1 req -> 2nd req -> 3rd
async await, recursion 


let name = 'masai'
// block scoped, redeclaration, hoisting
const lname = 'school'
// reassignment, redeclaration is not allowed and block scoped

function test(){
    // hoisting takes place
    console.log(name)
    var name = 'bangalore'
}

test()
<--->
let name = 'masai'
// block scoped, redeclaration, hoisting
const lname = ['nrupul','albert']
// reassignment, redeclaration is not allowed and block scoped
lname[0] = 'aman'

console.log(lname)

Arrow fucntions

sugar syntaxing, easier way to write functions

this keyword better


var person ={
    name: 'masai',
    display: ()=>console.log(this),
    displayES5: function(){
        console.log(this)
    }
}

// es6
person.display()
// es5
person.displayES5()



// call, apply, bind
// change the context of this


class App extends React.Component{
    constructor(props){
        super(props)
        this.state = {
            data: [1,2,3]
        }
        // this.handleClick = this.handleClick.bind(this)
    }
    handleClick=()=>{
        console.log(this.state.data)
    }
}

( context of that object )

PROTOTYPE
classes -> sugar syntax

constructor

function Person(name, age){
    this.name = name
    this.age = age
}

Person.prototype.display = function(){
    console.log(this.name)
}


// new
var person = Person('masai',25)


person.display()

CLASS

class Person{
    constructor(name,age){
        this.name = name
        this.age = age
        this.sleep()
    }
    sleep(){
        console.log(this.name,'is sleeping')
    }
}

class Coder extends Person{
    constructor(name,age,role){
        // super(name,age)
        this.role = role
    }

    code(){
        console.log(this.name,'is coding')
    }
    role(){
        console.log(this.name,'role is',this.role)
    }
    profile(){
        console.log(this.name, this.age, this.role)
    }
}


var person = new Person('masai',25)
var coder = new Coder('haren',21,'frontend')

coder.code()
coder.sleep()
coder.profile()

destructuring, default, promises, async await, Sets, Maps, BigInt 

BigInt
just add n after every number

var value = 2n**53n -1n

console.log(value, value+1000n)

console.log((value+100n)%10n)

var val = 2**53-1

console.log((val+100)%10)

EVENT LOOP

2-5 min

Javascript syncronous lang
async
its browser
Call stack 
Task queue 
If the call is not empty, then the task queue 
blocking code
overflow the stack
Promise has a higher priority

THIS
this refers to an object itself
call, apply, bind
functions, this is created function invoked
arrow fun dont have this
window
"use strict";

objects and arrays

var arr  = [1,2,3,4,5]
var obj = {
    name:'masai',
    place: 'blr'
}

Object.defineProperty(obj,'length',{
    value: 0,
    writable: false,
    enumerable: false
})

// console.log(Array.isArray(arr))

console.log(obj.hasOwnProperty('place'))

console.log(Object.getOwnPropertyNames(obj))

console.log(Object.keys(obj))

// non enumerable properties

console.log(++obj.length)
console.log(obj.length)

fetch vs axios
```

- CORS
- jQuery
- IIFE
- anonymous functions
- Sets, Map
- modules
- localStorage, cookie, sessionStorage
- ECMAScript, TC39
- polyfill
- tree shaking
- HTTP protocols
- Implementation of Stacks, Queues, Linked List, Trees (Binary Tree, Nary Tree), Graphs
- Traversing, reversing, mirror, and other operations for LinkedList, Trees, Graphs (1st, 2nd, 3rd level)


ES6 and others:

- var let const
- arrow functions
- template literals
- destructuring
- default params
- event loop
- promises, async, await, fetch, axios
- classes
- this
- inheritance, and prototype
- call apply bind
- getters
- setters
- generators
- yield
- BigInt
- Optional Chaining