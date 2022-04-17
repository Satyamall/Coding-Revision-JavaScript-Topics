Javascript Topics:

- primitives data types <a href="https://developer.mozilla.org/en-US/docs/Glossary/Primitive">Link</a>
- variables, string, numbers, booleans, undefined, null, NaN  <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures">Link</a>
- arithmetic operators <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators">Link</a>
- comparison operators <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators">Link</a>
- logical operators  <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators">Link</a>
- conditional statements (if else, switch) <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals">Link</a>
- functions, arguments, return statement, scope <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions">Link</a>
- callbacks <a href="https://developer.mozilla.org/en-US/docs/Glossary/Callback_function">Link</a>, higher order functions <a href="https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function">Link</a>
- for loops, while, do while <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration">Link</a>
- Arrays   <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array">Link</a>
    - declaration
    - accessing items
    - assignment
    - Array methods
    - 2D array
    - 3D array
    - forEach, map, reduce, filter callbacks
- Objects <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object">Link</a>
    - difference from arrays
    - key value pair
    - accessing values
    - assigning values
    - methods
    - for in loop
    - this
- hoisting  <a href="https://developer.mozilla.org/en-US/docs/Glossary/Hoisting">Link</a>

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
- scopes  <a href="https://www.w3schools.com/js/js_scope.asp">Link</a>
    - global 
    - local scope
    - block scope
- closures  <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures">Link</a>
- lexical scoping <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures#lexical_scoping">Link</a>
- Execution context <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this">Link</a>
- strict mode <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode">Link</a>
- solve problems faster by using objects 
- recursion <a href="https://developer.mozilla.org/en-US/docs/Glossary/Recursion">Link</a>

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

- DOM manipulation <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction">Link</a>, another <a href="https://www.w3schools.com/js/js_htmldom.asp">Link</a>
    - createElement
    - append
    - getElementById
    - querySelector
    - querySelectorAll
    - setAttribute
    - children methods
- event API, eventListener <a href="https://developer.mozilla.org/en-US/docs/Web/API/Event">Link</a>
- event bubbling <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_bubbling_and_capture">Link</a>
- event capturing <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_bubbling_and_capture">Link</a>
- style and attribute manipulation with DOM <a href="https://www.w3schools.com/jsref/prop_html_style.asp">Link</a>
- JSON <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON">Link</a>
- using AJAX / XHR <a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest">Link</a>
- callback, callback hell  <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing">Link</a>
- asyncrnonous behavior in javascript 
    - setTimeout  <a href="https://developer.mozilla.org/en-US/docs/Web/API/setTimeout">Link</a>
    - setInterval <a href="https://developer.mozilla.org/en-US/docs/Web/API/setInterval">Link</a>
- event loop <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop">Link</a>
    - call stack 
    - task/event queue
- WEB API <a href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction">Link</a>
- promises <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise">Link</a> OR <a href="https://www.w3schools.com/js/js_promise.asp">Link</a>
    - promise chaining
    - advantage over callbacks
- async, await  <a href="https://www.w3schools.com/js/js_async.asp">Link</a> OR <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function">Link</a>
- fetch API <a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch">Link</a>
- axios <a href="https://axios-http.com/docs/intro">Link</a>

DOCS for Above: <a href="http://www.w3schools.me/JavaScript/javascript-promise">Link</a>

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

- CORS <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS">Link</a>
- jQuery <a href="https://www.w3schools.com/jquery/default.asp">Link</a>
- IIFE  <a href="https://developer.mozilla.org/en-US/docs/Glossary/IIFE">Link</a>
- anonymous functions <a href="https://www.w3schools.com/js/js_function_definition.asp">Link</a>
- Sets, Map <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set">Link</a>
- modules <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules">Link</a>
- localStorage, <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage">Link</a> , 
cookie <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie">Link</a>, sessionStorage  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage">Link</a>
- ECMAScript <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Language_Resources">Link</a>, TC39 <a href="https://github.com/tc39/proposals">Link</a>
- polyfill <a href="https://developer.mozilla.org/en-US/docs/Glossary/Polyfill">Link</a>
- tree shaking <a href="https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking">Link</a> OR <a href="https://webpack.js.org/guides/tree-shaking/">Link</a>
- HTTP protocols <a href="https://developer.mozilla.org/en-US/docs/Glossary/https">Link</a>
- Implementation of Stacks, Queues, Linked List, Trees (Binary Tree, Nary Tree), Graphs 
- Traversing, reversing, mirror, and other operations for LinkedList, Trees, Graphs (1st, 2nd, 3rd level)


ES6 and others: <a href="https://www.w3schools.com/js/js_es6.asp">Link</a>

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