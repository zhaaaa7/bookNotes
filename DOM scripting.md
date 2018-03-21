
## chapter 1 History
### DHTML
DHTML is short for Dynamic HTML. Not a technology in and of itself, DHTML is a shorthand term for describing the combination of HTML, CSS, and JavaScript. The thinking behind DHTML went like this:
• You could use HTML to mark up your web page into elements.
• You could use CSS to style and position those elements.
• You could use JavaScript to manipulate and change those styles on the fly.

While the browser manufacturers simply wanted some way to manipulate web pages with JavaScript, the W3C proposed a model that could be used by any programming language to manipulate any document written in any markup language.


## chapter 2 javacript basics
### Dom
In short, the DOM is a way of conceptualizing the contents of a document.

The DOM is what’s known as an application programming interface (API). APIs are essentially conventions that are agreed upon by mutual consent.

In the world of programming, there are many different languages, but there are many similar tasks. That’s why APIs are so handy. Once you know the standard, you can apply it in many different environments. The syntax may change depending on the language you’re using, but the convention remains the same.

In fact, what binds (X)HTML, CSS, and JavaScript together is the DOM. So, let’s use a more accurate term to describe this process: DOM scripting. This refers to the manipulation of documents and style sheets using the W3C DOM. 


### compiler and interpreter
Programming languages are either interpreted or compiled. Languages like Java or C++ require a compiler. A compiler is a program that translates the source code written in a high-level language like Java into a file that can be executed directly by a computer.

Interpreted languages don’t require a compiler—they just need an interpreter instead. With JavaScript, in the context of the World Wide Web, the web browser does the interpreting. The JavaScript interpreter in the browser executes the code directly from the source. Without the interpreter, the JavaScript code would never be executed.

If there are any errors in the code written in a compiled language, those errors will pop up when the code is compiled. In the case of an interpreted language, errors won’t become apparent until the interpreter executes the code.

### weakly typing language
JavaScript makes no distinction in how they are declared or assigned. Some other languages demand that when a variable is declared, its data type is also declared. This is called typing.

Programming languages that require explicit typing are called strongly typed languages. Because typing is not required in JavaScript, it is a weakly typed language. This means that you can change the data type of a variable at any stage.

### escaping
```
var mood = "don't ask";
```
If you wanted to write that statement with single quotes, you would need to ensure that the apostrophe (or single quote) between the n and the t is treated as part of the string. In this case, the single quote needs to be treated the same as any other character, rather than as a signal for marking the end of the string. This is called escaping. In JavaScript, escaping is done using the backslash character:
```
var mood = 'don\'t ask';
```

## Arrays
Strings, numbers, and Boolean values are all examples of scalars. If a variable is a **scalar**, then it can only ever have one value at any one time. If you want to use a variable to store a whole set of values, then you need an array.
In JavaScript, you declare an array by using the Array keyword. You can also specify the number of elements that you want the array to contain. This number is the length of the array:
```
var beatles = Array(4);
```
Sometimes you won’t know in advance how many elements an array is eventually going to hold. That’s OK. Specifying the number of elements is optional. You can just declare an array with an unspecified number of elements:
```
var beatles = Array();
```
Adding elements to an array is called **populating** it. When you populate an array, you specify not just the value of the element, but also where the element comes in the array. This is the index of the element. Each element has a corresponding index. The index is contained in square brackets:
```
array[index] = element;
```
### operator
If you use a single equal sign in a conditional statement, the operation will always be true as long as the assignment succeeds.
```javascript
var my_mood = "happy";
var your_mood = "sad";
if (my_mood = your_mood) {
  alert("We both feel the same."); //always executed
} 
```

### function
A function is a group of statements that can be invoked from anywhere in your code. Functions are, in effect, miniature scripts.

If you use var within a function, the variable will be treated as a local variable. It only exists within the context of the function. If you don’t use var, the variable will be treated as a global variable. If there is already a variable with that name, the function will overwrite its value.
```javascript
function square(num){
  total = num * num;
  return total; 
}
var total = 50;
var number = square(20); 
alert(total);  //400
```

### object
There is one very important data type that we haven’t looked at yet: objects. An object is a self-contained collection of data. This data comes in two forms: properties and methods:
• A property is a variable belonging to an object.
• A method is a function that the object can invoke.
These properties and methods are all combined in one single entity, which is the object.
Properties and methods are both accessed in the same way using JavaScript’s dot syntax:
```
Object.property 
Object.method()
```

#### native objects
The Array object is an example of a native object supplied by JavaScript. Other examples include Math and Date, both of which have very useful methods for dealing with numbers and dates respectively.

#### host objects
Another kind of object is supplied not by the JavaScript language itself, but by the environment in which it’s running.  In the case of the Web, that environment is the web browser. Objects that are supplied by the web browser are called host objects.

Host objects include Form, Image, and Element. These objects can be used to get information about forms, images, and form elements within a web page. There is another object that can be used to get information about any element in a web page that you might be interested in: the document object.


## chapter 3 Document Object Model
### objects in js
There are three kinds of objects in JavaScript:
• User-defined objects created from scratch by the programmer. 
• Native objects like Array, Math, and Date, which are built in to JavaScript.
• Host objects that are provided by the browser.

### Browser Object Model
From the earliest days of JavaScript, some very important host objects have been made available for scripting. The most fundamental of these is the window object.
The window object is nothing less than a representation of the browser window itself. The properties and methods of the window object are often referred to as the Browser Object Model (although perhaps Window Object Model would be more semantically correct). The Browser Object Model has methods like window.open and window.blur. 

we’ll focus on what’s **inside** the browser window. The object that handles the **contents of a web page** is the document object.

### model
The M in DOM stands for Model, but it could just as easily stand for Map. A model, like a map, is a representation of something. The DOM represents the web page that’s currently loaded in the browser window. The browser provides a map (or model) of the page. You can use **JavaScript to read this map**.

In order to gain information from the model, you need to understand what conventions are being used to represent the document.

The most important convention used by the DOM is the representation of a document as a tree. More specifically, the document is represented as a family tree.

The root element is html. For all intents and purposes, the html element is the document.

However, instead of using the term family tree, it’s more accurate to call a document a node tree.

### node
The term node comes from networking, where it used to denote a point of connection in a network. A network is a collection of nodes.

A document is a collection of nodes, with nodes as the branches and leaves on the document tree.

#### element node
Elements are the basic **building blocks** of documents on the Web, and it’s the arrangement of these elements in a document that gives the document its **structure**. The tag, such as `<body>, <p>, and <ul>` provides the **name of an element**.
  
#### text node
If a document consisted purely of empty elements, it would have a structure, but the document itself wouldn’t contain much content.
```
<p>Don’t forget to buy this stuff.</p>
```
In our example, the <p> element contains the text “Don’t forget to buy this stuff.” This is a text node.
In XHTML, text nodes are always enclosed within element nodes. But not all elements contain text nodes. 
  
#### attribute node
Attributes are used to give more specific information about an element. The title attribute, for example, can be used on just about any element to specify exactly what the element contains:
```
<p title="a gentle reminder">Don't forget to buy this stuff.</p>
```

<img src="https://github.com/zhaaaa7/bookNotes/blob/master/img/nodes.png" alt="nodes" width="400px"/>

### Cascading Style Sheets
The DOM isn’t the only technology that **interacts with the structure of web pages**. CSS is used to instruct a browser how to display the contents of a document.

**Inheritance** is a powerful feature of CSS. Like the DOM, CSS views the contents of a document as a node tree. Elements that are nested within the node tree will inherit the style properties of their parents.
For instance, declaring colors or fonts on the body element will automatically apply those styles to all the elements contained within the body:
```
body {
  color: white;
  background-color: black; 
}
```
When you’re applying styles to a document, there are times when you will want to target specific elements. o get this level of precision, you need to insert something into the document itself to **mark the paragraph as a special case**. To mark elements for special treatment, you can use one of two attributes: **class or id**.

**The id attribute acts as a kind of “hook” that can be targeted by CSS. The DOM can use the same hook.**

### Getting Elements
#### getElementById
Three handy DOM methods allow you to access element nodes by ID, tag name, and class name.
```
document.getElementById(id)
```
allows you to get straight to the **element node with the specified id**.

This is referencing the unique element that has been assigned the HTML id attribute "purchases" in the document object. This element also corresponds to an **object**.

In fact, **each element in a document is an object**. Using the DOM, you can “get” at all of these elements.

#### getElementsByTagName
If you use the method getElementsByTagName, you have instant access to an **array** populated with every occurrence of a specified tag.

Every value in the array is an object.
```
var items = document.getElementsByTagName("li"); 
for (var i=0; i < items.length; i++) {
  alert(typeof items[i]); 
}
```

#### getElementsByClassName
It also behaves in the same way as getElementsByTagName by returning an array of elements with a common class name. 
You can also include multiple class names to locate elements that have more than one class. 
```
alert(document.getElementsByClassName("important sale").length);
```
**The order of the class names doesn’t matter, and it would match if the element had additional class names as well.**

### Getting and Setting Attributes -- works only on element nodes
Once you have the element, you can find out the values of any of its attributes. You can do this with the getAttribute method. And using the setAttribute method, you can change the value of an attribute node.

#### getAttribute
getAttribute is a function. It takes only one argument, which is the attribute that you want to get: 
```
object.getAttribute(attribute)
```
```javascript
var paras = document.getElementsByTagName("p"); 
for (var i=0; i< paras.length; i++) {
  var title_text = paras[i].getAttribute("title");
  if (title_text) {
    alert(title_text); 
  }
}
```

#### setAttribute
It allows you to change the value of an **attribute node**. 
setAttribute takes two arguments: 
```
object.setAttribute(attribute,value)
```
In the following example, we’re getting the element with the id "purchases" and giving it a title attribute with the value "a list of goods".
```
var shopping = document.getElementById("purchases"); 
shopping.setAttribute("title","a list of goods");
```

### dynamic changing
Note that even when a document has been changed by setAttribute, you won’t see that change reflected when you use the view source option in your web browser. This is because the **DOM has dynamically updated the contents of the page after it has been loaded. The real power of the DOM is that the contents of a page can be updated without refreshing the page in the browser.**


## Chapter 4 A image gallary
### A callback function
You can put the navigation for the entire gallery on one page and then download each image as, and when, it’s required.
1. Put a placeholder image on the same page as the list.
2. When the user clicks a link, intercept the default behavior.
3. Replace the placeholder image with the image from the link.

In order to swap out the placeholder image, I need to change its src attribute.
```javascript
function showPic(whichpic){
  var placeholder=document.getElementById("placeholder").
  var source=showpic.getAttribute("href");
  placeholder.setAttribute("src", source);
  // or, placeholder.src = source;
}
```
### Event handlers
Event handlers are used to **invoke some JavaScript** when a certain **action** happens. If you want some behavior to be triggered when the user moves their cursor over an element, you use the onmouseover event handler. There’s a corresponding onmouseout event.

showPic() expects one argument: an element node that has an href attribute. When I place the onclick event handler in a link, I want to send that link to the showPic function as the argument. Luckily, there’s a very short but powerful way of doing just that. The keyword this is a shorthand way of saying **“this object.”** In this case, I’ll use this to mean **“this `<a>` element node”:**
```
showPic(this)
```

I can add that using the onclick event handler. Here’s the syntax for adding JavaScript using an event handler:
```javascript
event = "JavaScript statement(s)"

//This will invoke the showPic function with the onclick event handler
onclick = "showPic(this);"
```
However, if I simply add this event handler to a link in my list, I’ll be faced with a problem. The function will be invoked, **but the default behavior for clicking on a link will also be invoked**. This means that the user will be taken to the image—exactly what we didn’t want to happen. I need to **stop the default behavior from being invoked**.

Let’s take a closer look at how event handling works. When you attach an event handler to an element, you can trigger JavaScript statements with the event. The JavaScript can return a result that is then passed back to the event handler. For example, you can attach some JavaScript to the onclick event of a link so that it returns a Boolean value of true or false. If you click the link, and the event handler receives a value of true, it’s getting the message “yes, this link has been clicked.” If you add some JavaScript to the event handler so that it returns false, then the message being sent back is “no, this link has not been clicked.”
```
<a href="http://www.example.com" onclick="return false;">Click me</a>
```
If you click that link, the default behavior will not be triggered, because the JavaScript is effectively canceling the default behavior.

### childNodes
The childNodes property is a way of getting information about the children of any **element** in a document’s node tree. 
```
element.childNodes
```

```javascript
function countBodyChildren() {
  var body_element = document.getElementsByTagName("body")[0]; //there is only one body element node
  alert (body_element.childNodes.length); 
}

window.onload = countBodyChildren;
```
**Note**: The childNodes property returns an array containing **all types of nodes**, not just element nodes. It will bring back all the attribute nodes and text nodes as well. In fact, just about everything in a document is some kind of node. Even **spaces and line breaks** are interpreted as nodes and are included in the childNodes array.

### nodeType property 
This will tell us exactly what kind of node we’re dealing with. 
```
node.nodeType
```
**Note:** However, instead of returning a string like “element” or “attribute,” it returns a number.
There are 12 possible values for nodeType, but only three of them are going to be of much practical use:
• Element nodes have a nodeType value of 1.
• Attribute nodes have a nodeType value of 2.
• Text nodes have a nodeType value of 3.

### nodeValue]
```
alert (description.nodeValue); //null
```
This will return a value of null. The nodeValue of the paragraph element itself is empty. What you actually want is the value of the text within the paragraph.
**The text within the paragraph is a different node**. 
```
alert(description.childNodes[0].nodeValue); // Choose an image
```
updating the text node of a p tage
```javascript
function showPic(whichpic) {
  var source = whichpic.getAttribute("href");
  var placeholder = document.getElementById("placeholder");
  placeholder.setAttribute("src",source);
  var text = whichpic.getAttribute("title");
  var description = document.getElementById("description"); 
  description.firstChild.nodeValue = text;
}
```

## chapter 5 Best practice
What this chapter covers:
• Graceful degradation: ensuring that your web pages still work without JavaScript
• Unobtrusive JavaScript: separating structure from behavior
• Backward compatibility: ensuring that older browsers don’t choke on your scripts
• Performance considerations: making sure that your script is performing at its best

### graceful degradation
When a technology degrades gracefully, the functionality may be reduced, but it doesn’t fail completely.

### Unobtrusive JavaScript
Using an attribute like onclick in the markup is just as inefficient as using the style attribute. It would be much better if we could use a **hook, like class or id**, to tether the behavior to the markup without intermingling it. You can attach an event to an element in an external JavaScript file:
```
element.event = action;
```
```javascript 
window.onload = prepareLinks; // ensure the document has finished loading
var links = document.getElementsByTagName("a"); 
for (var i=0; i<links.length; i++) {
  if (links[i].getAttribute("class") == "popup") { 
    links[i].onclick = function() {
      popUp(this.getAttribute("href"));
      return false; 
    }
  } 
}
````
### Backward compatibility
Most browsers support JavaScript to some degree, and modern browsers have excellent support for the DOM.So even if a user visits your site with a browser that supports some JavaScript, some of your scripts may not work.

Testing for the existence of a specific property or method that you’re about to use in your code is the safest and surest way of ensuring backward compatibility.

#### Browser sniffing
There is another technique that was very popular during the dark days of the browser wars. Browser sniffing involves extracting information provided by the browser vendor.

### Performance considerations
#### Minimizing DOM access and markup
#### Assembling and placing scripts
#### Minification
In most cases, you’ll need to keep **two copies**: a working copy, in which you can make changes and comments, and the minified copy, which you serve up on your site. 

## chapter 6 revisite image gallery
### DOM Core and HTML-DOM
So far, I’ve been using a small set of methods to accomplish everything I want to do, including
• getElementById
• getElementsByTagName
• getAttribute
• setAttribute
These methods are all part of the DOM Core. They aren’t specific to JavaScript, and they can be used by any programming language with DOM support. They aren’t just for web pages, either. These methods can be used on documents written in any markup language (XML, for instance).
When you are using JavaScript and the DOM with HTML files, you have many more properties at your disposal. These properties belong to the **HTML-DOM**, which has been around longer than the DOM Core.
```
document.getElementsByTagName("form")

document.forms

```

## Chapter 7 create markup on the fly
It is also possible to use JavaScript to change the structure and contents of a web page. In this chapter, you’ll learn about some DOM methods that can **alter the structure of a web page by creating new elements and modifying existing ones**.

### Some old-school methods
document.write
```
<script>
  document.write("<p>This is inserted.</p>");
</script>
```
### innerHTML
```
<div id="testdiv">
  <p>This is <em>my</em> content.</p> 
</div>
```
<img src="https://github.com/zhaaaa7/bookNotes/blob/master/img/innerhtml1.png" alt="innerHTML1" width="400px" />

<img src="https://github.com/zhaaaa7/bookNotes/blob/master/img/innerhtml2.png" alt="innerHTML1" width="400px" />
