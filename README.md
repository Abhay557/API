# What is an API? (Application Programming Interface)

API is the acronym for Application Programming Interface,
which is a software intermediary
that allows two applications to talk to each other.
Each time you use an app like Discord, send an instant message,
or check the weather on your phone, you’re using an API.

## What Is an Example of an API?

When you use an application on your mobile phone, the application connects to the Internet and sends data to a server. The server then retrieves that data, interprets it, performs the necessary actions and sends it back to your phone. The application then interprets that data and presents you with the information you wanted in a readable way. This is what an API is - all of this happens via API.

To explain this better, let us take a familiar example.

Imagine you’re sitting at a table in a restaurant with a menu of choices to order from. The kitchen is the part of the “system” that will prepare your order. What is missing is the critical link to communicate your order to the kitchen and deliver your food back to your table. That’s where the waiter or API comes in. The waiter is the messenger – or API – that takes your request or order and tells the kitchen – the system – what to do. Then the waiter delivers the response back to you; in this case, it is the food.

Here is a real-life API example. You may be familiar with the process of searching flights online. Just like the restaurant, you have a variety of options to choose from, including different cities, departure and return dates, and more. Let us imagine that you’re booking you are flight on an airline website. You choose a departure city and date, a return city and date, cabin class, as well as other variables. In order to book your flight, you interact with the airline’s website to access their database and see if any seats are available on those dates and what the costs might be.

## How To Make A Basic API On Autocode

```
/**
 * An example typed API that generates a hello world message
 *   Read more about typing at: https://github.com/acode/functionscript
 * @param {string} name The name to say hello to
 * @param {integer} count The number of times to say hello
 * @returns {object} body
 * @ {array} messages A list of messages
 */
module.exports = async (name = 'world', count = 10) => {
  count = Math.min(Math.max(1, count), 100);
  return {
    messages: Array(count).fill(`Hello ${name}, welcome to Autocode ${count} times!`)
  };
};
```

If you've worked on other Autocode projects, you might notice that this endpoint   
looks a bit different from standard webhook endpoints. That's because this
endpoint defines its parameters and return types using 
[FunctionScript](https://github.com/acode/functionscript), Autocode's specification
for turning functions into type-safe HTTP APIs. The comment block 
(lines between `/**` and `*/`) is where everything happens.
Here's more detail on what each line does:

- The lines before the first `@param` describe what the API does.
- `@param {string} name The name to say hello to` declares that the endpoint will take a `string` parameter called `name`.
- `@param {integer} count The number of times to say hello` declares that the endpoint will take a `integer` parameter called `count`.
- `@returns {object} body` declares that the API will return an `object`.
- `@ {array} messages A list of messages` applies to the previous line, and declares that the object the endpoint returns will contain an array property called `messages`.
- `module.exports = async (name = 'world', count = 10) => {` sets default values of `'world'` and `10` for `name` and `count`. These will be used if the incoming request does not have values for those parameters.

**Note:** The comment block must go *immediately* above the line that exports the 
function (`module.exports`).

If a request comes in that doesn't match this typing (for example, a request that
passes in a non-integer `count` parameter like `'hello'`), Autocode will reject the request and your
code will not run. Additionally, if your function returns a value that does not
match the return type, your function will automatically return an error (though 
the code will still run). 

You can designate parameters as optional by using `null` as a default value.
For more on what you can do with FunctionScript, including a full list of types,
check out [the official docs](https://github.com/acode/functionscript).

https://youtu.be/Y9HIMlPMANk
<h3>Another Example</h3>

```
let messagePrompts = [
'Number 1',
'Number 2',
'Number 3',
'Number 4',
'Number 5',
'Number 6',
'Number 7',
'Number 8',
'Number 9',
'Number 10',
];
  let messageChoice = Math.floor(Math.random() * messagePrompts.length);
  let message = messagePrompts[messageChoice];
  return (message)
```

![Image](https://abhay557.public.files.stdlib.com/_stdlib/provider/Abhay557/images/s.jpg)
 Ship-Release It With All Enivorments!

Basic API-https://autocode.com/lib/abhay557/basic/

Thread By Abhay557 
