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

* **Interpolate using expression, in addition to variable**

{% code-tabs %}
{% code-tabs-item title="Interpolation.js" %}
```javascript
let isWorld = true;

let printStr1 = "Hello " + isWorld ? "World" : "me";
console.log(printStr1); //World

//Need to use () to wrap expression
let printStr2 = "Hello " + (isWorld ? "World" : "me");
console.log(printStr2); //Hello World
```
{% endcode-tabs-item %}
{% endcode-tabs %}

* **Multi-lines string**

{% code-tabs %}
{% code-tabs-item title="MultiLineString.js" %}
```javascript
let rhyme = "Are you sleeping? Are you sleeping?\nBrother John, Brother John!\nMorning bells are ringi
ng!\nMorning bells are ringing!\nDing, ding, dong.\nDing, ding, dong.";
```
{% endcode-tabs-item %}
{% endcode-tabs %}

* **HTML Raw Template**

{% code-tabs %}
{% code-tabs-item title="HTMLRaw.js" %}
```javascript
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
{% endcode-tabs-item %}
{% endcode-tabs %}

* **Paragraph strings with indentation**

{% code-tabs %}
{% code-tabs-item title="Paragraph.js" %}
```javascript
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
{% endcode-tabs-item %}
{% endcode-tabs %}

* **Having both single quote\('\) and double quotes\("\) in a string**



{% code-tabs %}
{% code-tabs-item title="SingleAndDoubleQuote.js" %}
```javascript

let introduction = 'My name is "John", I' + "'m using single quote (') and double quote " + '(") here';
```
{% endcode-tabs-item %}
{% endcode-tabs %}

For all the above pain points, we have a single solution i.e. _**Template Literals.**_

## What is template literals?

Template literals are string literals allowing embedded expressions.

In all the above-mentioned pain points, **readability** is the major concern. Let's try to solve the each pain point using _template literals._

* **Interpolate using expression, in addition to variable**

```text
let welcome = `Hello ${isWorld ? "World" : "me"}!`;
```

* **Multi-lines strings and indented strings**

```text
let paragraph = 
`Paragraph:
    1. Point 1:
       1.1 Sub-point 1:
       1.2 Sub-point 2:
    2. Point 2:
       2.1 Sub-point 1:
       2.2 Sub-point 2:
    3. Point 3:
       3.1 Sub-point 1:
       3.2 Sub-point 2:
Conclusion: I'm exhausted! Did I miss anything?`;
console.log(paragraph);
```

* **HTML templates**

```text
function personTemplate({name, hobbies, job}){
   return `<article class="person">
   <h3>${name}</h3>
   <div>
       <div>Hobbies:</div>
       <ul>
           ${hobbies.map(hobby => `<li>${hobby}</li>`).join(" ")}
       </ul>
   </div>
   <p>Current job: ${job}</p>
</article>`;
}
```

* **Having both single quote\('\) and double quotes\("\) in a string** 

```text
let introduction = `My name is "Maya Shavin", I'm using single quote (') and double quote (") here`;
```



