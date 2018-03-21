
## chapter 1 
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

