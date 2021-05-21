# JavaScript-WTFs-Personal-Collection

This my **personal favourite** collection of JavaScript WTF's... actually
*not really wtf's*, JS does have some strange core mechanics but 90% of them or even 99% could 
be well explained. 

Here i will post some tiny code examples that when you get to know it - you learn something new
about JavaScript and undestand it's code mechanics little deeply

Each item will have explanation in spoiler section, but i recommend you try to remind solution
first, and if you can't - open spolier. 
There is also a flag **head compiled** with a datestamp, that signals if i understand this example 
automatically in head or need to remind myself some tiny knowledges. If **head compiled** flag is true
then i find this item explicitly clear to understand.

## Item 1 
```javascript
let obj = { 
  1: "Hello, world!", 
  false : "Hello, Bill Gates!", 
  "1": "Hello, Putin",
  bool : "Hello, mr.President"
}
```
*What are the results of:*
```javascript
1) obj[undefined == null]
2) obj[undefined === null]
3) obj[1+""]
4) obj[typeof false]
```
<details>
  <summary>Explanation</summary>
  
  Spoiler text. Note that it's important to have a space after the summary tag. You should be able to write any markdown you want inside the `<details>` tag... just make sure you close `<details>` afterward.
  
  ```javascript
  console.log("I'm a code block!");
  ```
  
</details>

## Item 2 
```javascript
if ( [] ) console.log('Hello, World!')
if ( [] == false ) console.log('Hello, World!')
```
*Why both **if's** resolve to true ?*
*empty array [] in 1st condition is true and false in 2nd, why ?*

<details>
  <summary>Explanation</summary>
  
  Spoiler text. Note that it's important to have a space after the summary tag. You should be able to write any markdown you want inside the `<details>` tag... just make sure you close `<details>` afterward.
  
  ```javascript
  console.log("I'm a code block!");
  ```
  
</details>

## Item 3
```javascript
[] == ![]
```
*Why this condition resolves to true ? How could one entity be equal to negative self (or **not self**) ?*
*Explain in steps how this condition would be resolved in JavaScript*

<details>
  <summary>Explanation</summary>
  
  Spoiler text. Note that it's important to have a space after the summary tag. You should be able to write any markdown you want inside the `<details>` tag... just make sure you close `<details>` afterward.
  
  ```javascript
  console.log("I'm a code block!");
  ```
  
</details>

## Item 4
```javascript
const x = {
  i: 1,
  valueOf: function() {
    this.i++
  }
}

if (x==1 && x==2 && x==3)
  console.log('JS is great!')
```

*Why if statement resolves to true, explain how it works ?*
*How x==1 comparing works in this situation ?*

<details>
  <summary>Explanation</summary>
  
  Spoiler text. Note that it's important to have a space after the summary tag. You should be able to write any markdown you want inside the `<details>` tag... just make sure you close `<details>` afterward.
  
  ```javascript
  console.log("I'm a code block!");
  ```
  
</details>

## Item 5
  What for ArrayBuffer is used in JavaScript ? What classes for byte arrays do you know ? 
Describe a simple usage of ArrayBuffer and usecase.
<details>
  <summary>Answer</summary>
</details>
  
## Item 6
  ```javascript
  void(1)
  ```
  What is a **void** operator in JavaScript ? How does it work , define some simple usecases
  <details>
    <summary>Answer</summary>
    Void operator may be called as a function, f.x. - void(expression): void(5+5) or in this notation - void 3
    It always returns undefined and usually used in place where returning undefined is neccessary, f.x. in href 
    attribute in links, so the link won't follow
    
    ```javascript
    <a href="javascript:void(0);">
      Click here to do nothing
    </a>

    <a href="javascript:void(document.body.style.backgroundColor='green');">
      Click here for green background
    </a>
    ```
  </details>

## Item 7
What is **IIFE** and why it is used in JavaScript ? **Name different ways** of declaring **IIFE**: at least 2 ways, at max 5
  
  <details>
    <summary>Answer</summary>
    IIFE stands for Immediatly Invoked Function Expression and is used in many different situations in JavaScript. In times when no 'let' operator
    existed IIFE was used to wrap some code in separate function and hence isolate variables in function local lexical environment. Also IIFE is 
    good if there is a need to immediatly call declared function, f.x. invoke code of outside script.
    
    Ways of declaring IIFE:
    ```javascript
      Regular(simple) ones: 
        1. (function() {})()
        2. (function() {}())
      Some extra(not obvious) ones:
        1. void function() {}()
        2. +function() {}()
        3. !function() {}()
    ```
  </details>
  
## Item 8
How doesn dot notation work in JavaScript, what type of object it returns ? Explain why following example won't work as expected:
```javascript
let obj, method;

obj = {
  go: function() { alert(this); }
}
  
(method = obj.go)()      // will return undefined
(obj.go || obj.stop)()   // will return undefined
```

<details>
  <summary>Answer</summary>
  Dot notation in accompany with method calls in JavaScript returns special object of type [ReferenceType]
  [ReferenceType]:https://tc39.es/ecma262/#sec-reference-specification-type
  This means that after you invoke method via dot notation - user.sayhi(), .(dot) here returns ReferenceType
  which includes:
  1. **base** - object its called at
  2. **name** - method name
  3. **strict** - strict mode: true/false  
    
  This ReferenceType is lost if there is any type of expression(regular (=), logic(&&, ||, !)) in between
  call () and a dot notation. For example in (method = obj.go)(), there is a equating before method call.
</details>
