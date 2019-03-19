---
description: Gives the clear idea about the ES6 concepts
---

# Template Literals

## Strings in JavaScript

When template strings are not supported, we used Javascript's strings and they are provided with simple functionalities -- such as:

* **Creation:**

```javascript
let str1 = 'hello'; //single quote
let str2 = "world"; //double quote
let str3 = String('hello world');
```

* **Modification:** 

```javascript
str1.replace('he', 'ha'); // hallo
str1 = str1 + " " + str2;
```

* **Concatenation:** 

```javascript
const name = 'John';
const wishes = str1 + ", my name is " + name;
```

So far, it's pretty cool and our code is readable. Now, let's see the some situations where the readability is missed.

## Pain points with Javascript's String

* **Long strings:**

```javascript
let longStr = "I'm a super long long long long long long\" + 
" long long long long long long\" +
" long long long long long long\" +
" long long long long long long\" +
" text. Check me out!";
```

* **Interpolate using expression, in addition to variable?**

```text
let isWorld = true;
let printStr1 = "Hello " + isWorld ? "World" : "me";
console.log(printStr1); //World

//Need to use () to wrap expression
let printStr2 = "Hello " + (isWorld ? "World" : "me");
console.log(printStr2); //Hello World
```

* **Multi-lines string**

```text
let rhyme = "Are you sleeping? Are you sleeping?\nBrother John, Brother John!\nMorning bells are ringing!\nMorning bells are ringing!\nDing, ding, dong.\nDing, ding, dong.";
```

* **HTML Raw Template**

```text
let person = {
    name: "Maya",
    hobbies: ["reading", "drawing", "traveling"],
    job: "Developer"
};
function personTemplate(person){
    return "<article class='person'>" +
                "<h3>" + person.name + "</h3>" +   
                "<p> Hobbies: " + person.hobbies +  "</p>" +
                "<p> Current job: " + person.job + "</p>" +                         
           "</article>";
}
document.write(personTemplate(person));
```

* **Paragraph strings with indentation**

```text
let paragraph = "Paragraph: \n" +
"\t1. Point 1:\n" +
"\t\t1.1 Sub-point 1:\n" +
"\t\t1.2 Sub-point 2:\n" +
"\t2. Point 2:\n" +
"\t\t2.1 Sub-point 1:\n" +
"\t\t2.2 Sub-point 2:\n" +
"\t3. Point 3:\n" +
"\t\t3.1 Sub-point 1:\n" +
"\t\t3.2 Sub-point 2:\n" +
"Conclusion: I'm exhausted! Did I miss anything?";
console.log(paragraph);
```

* **Having both single quote\('\) and double quotes\("\) in a string**



```text
let introduction = 'My name is "John", I' + "'m using single quote (') and double quote " + '(") here';
```

For all the above pain points, we have a single solution i.e. _**Template Literals.**_

## What is template literals?

Template literals are string literals allowing embedded expressions.

In all the above-mentioned pain points, **readability** is the major concern. Let's try to solve the each pain point using _template literals._

* **Long strings**

