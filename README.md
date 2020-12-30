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
```js
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
  toString: function() {
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
