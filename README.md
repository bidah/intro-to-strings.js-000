# JavaScript Strings

## Objectives
+ Use string concatenation
+ Use JS string convenience methods 
+ Convert string to number data type


Just like in Ruby, JavaScript has a handle of convenience methods built into the language that allow us to easily manipulate and modify strings. You can read all about Strings in JS, and even more methods [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

Feel free to open up the Developer Tools in Chrome or Firefox to play around with these methods.

## Concatenation

Unlike Ruby, JavaScript doesn't come with a prior knowledge of how to interpolate a variable (remember, interpolation in Ruby looks like this: `"Hi, my name is #{name}"`). 

Instead, when you want to combine several variables into one long string, you must concatenate.

```js
var name = "cricky";
console.log("Hi my name is " + name);
//this will print "Hi my name is cricky"
```
JavaScript does something unusual when you add a string with a number:

```javascript
var hours = 10;
var species = "sloths";

// the line below prints "sloths sleep 10 hours a day"
console.log(species + " sleep " + hours + " hours a day");
```

You'll notice in the example above, the variable `hours` is storing a number, while the rest of the sentence is a string. When adding a number and a string, JavaScript automatically transforms the number into a string.

## Length

Calling `length` on a string will return the number of characters in that string.

```javascript
var species = "mantis shrimp";

// the line below will print 13
console.log(species.length);
```

## Changing Case

The two common functions to change the case of a string are `toUpperCase()`  and `toLowerCase()`. It's important to note that when you call a function that doesn't require a parameter, like `toUpperCase()` and `toLowerCase()` does need to be invoked with `()`. 

```javascript
"I'm not shouting!!!".toUpperCase();
// => "I'M NOT SHOUTING!!!"

"I'M A CONSCIENTIOUS LIBRARIAN.".toLowerCase();
// => "i'm a conscientious librarian."
```
You may notice that there is no pre-built `capitalize()` method. To capitalize just the first letter of a string, you'll have to make your own custom method.

## Replacing Characters

To replace characters with new characters, you can use the `replace()` method. It works similarly to Ruby's `gsub` method in that the first parameter is the set of characters you would like to remove and the second is the string you would like to add instead.

```javascript
var sentence = "pandas have two compound eyes and a proboscis".replace("pandas", "butterflies");
// => "butterflies have two compound eyes and a proboscis"
sentence.replace("two compound eyes", "two antennae")
// => "butterflies have two antennae and a proboscis"
```

Notice that the `replace()` will replace only the first occurrence:

```javascript
var quote = "xylophone phone home";
quote.replace("o", "*");

// quote is now "xyl*phone phone home"
```

The string class' `replace()` function can also take Regex for the first parameter:

```javascript
var phoneNumber = "5556768799";

// the line below will return "(555) 676 - 8799"
phoneNumber.replace(/(\d{3})(\d{3})(\d{4})/, '($1) $2 - $3');
```

## Turn String to Number

Two different functions to turn are `parseInt(`) and `Number()`. The `Number` function creates a new number, while the `parseInt` function parses the string. Check out [this stack overflow post](http://stackoverflow.com/questions/4090518/what-is-the-difference-between-parseint-and-number) for more information. 

```javascript
Number("78");
// => 78
parseInt("78");
// => 78
Number("20px");
// => NaN
parseInt("20px");
// => 20

```

## Slice

The `slice()` method extracts a section of a string and returns a new string. It accepts one required parameter, the index to start on, and one optional parameter, the index to end on.

```javascript
var sentence = "They misunderestimated me.";
var word = sentence.slice(5, 22);

// the line below prints "misunderestimated"
console.log(word); 
```

Like in Ruby, you can also use negative indices with strings:

```javascript
var bushism = "They misunderestimated me.";
var word = bushism.slice(5, -4);

// the line below prints "misunderestimated"
console.log(word); 
```

## Split

The `split()` method splits a String object into an array of strings by separating the string into substrings.

```javascript
var longString = "Jan,Feb,Mar,Apr,May,Jun";
var months = longString.split(",");

// months is now ["Jan","Feb","Mar","Apr","May","Jun"]
```

## Resources

* [Codecademy -  Strings](http://www.codecademy.com/glossary/javascript/strings)
* [StackOverflow - What's the fastest way to convert String to Number in JavaScript?](http://stackoverflow.com/a/12862627/2890716)
* [StackOverflow - Capitalize the first letter of string](http://stackoverflow.com/a/1026087/2890716)
* [StackOverflow - Replacing all occurrences of a string in JavaScript](http://stackoverflow.com/a/1144788/2890716)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/intro-to-strings.js' title='JavaScript Strings'>JavaScript Strings</a> on Learn.co and start learning to code for free.</p>
