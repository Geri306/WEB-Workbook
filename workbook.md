# Web Module Questions

### Functional patterns

#### What is a callback function?

> a function passed into another function as an argument, which is then invoked inside the outer function to complete some action <br>[MDN - Callback function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)

#### What is ECMA script ? What is the difference between Javascript & ECMA script ?

> JavaScript is a general-purpose scripting language that conforms to the ECMAScript specification. The ECMAScript specification is a blueprint for creating a scripting language. JavaScript is an implementation of that blueprint. On the whole, JavaScript implements the ECMAScript specification as described in ECMA-262. <br>[Cloudacademy - difference between ECMAScript and JavaScript](https://cloudacademy.com/course/the-difference-between-ecma-script-and-javascript/the-difference-between-ecmascript-and-javascript/#:~:text=JavaScript%20is%20a%20general%2Dpurpose,as%20described%20in%20ECMA%2D262.)

#### What is the difference between `let` & `var` ?

> **let:** block-scoped, can't be redeclared, hoisting doesn't occur
>
> **var:** function scoped, can be redeclared, hoisting occurs
>
> [Programiz](https://www.programiz.com/javascript/let-vs-var)

#### Write an example where using the `var` declaration instead of the `let` could create a hard to debug code.

<p>Var can be updated and redeclared within the same scope without getting an error. The second variable you declared with var overwrites the first one. This might cause you to accidentally overwrite the value of the existing variable with the same name and debugging becomes hard in this situation.</p>

```javascript
var variable = "Steve Harrington";
var variable = "Will Barley";

console.log(variable);

// result: Will Barley => hard debugging because of no error message
```

#### Give a practical example where you would use the `reduce` function in javascript.

> Sum the values in an array of objects

> To sum up the values contained in an array of objects, you **must** supply an `initialValue`, so that each item passes through your function.

```javascript
const objects = [{ x: 1 }, { x: 2 }, { x: 3 }];
const sum = objects.reduce((previousValue, currentValue) => previousValue + currentValue.x, 0);

// initial Value: starting value (like let i = 0)

console.log(sum); // logs 6
```
> [MDN - Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce#sum_of_values_in_an_object_array)

#### Give a practical example where you would use the `map` function in javascript.

<p>For iterating over an array and calling function on every element of array</p>

```javascript
const array = [3, 4, 5, 6, 7];

const newArray = array.map(function (element, index) {
  return { key: index, value: element + element };
});

console.log(newArr);

// result:

[
  { key: 0, value: 6 },
  { key: 1, value: 8 },
  { key: 2, value: 10 },
  { key: 3, value: 12 },
  { key: 4, value: 14 },
];
```

#### Give a practical example where you would use the `filter` function in javascript.

> For filtering out specific elements of an array or object which meet some kind of criteria.

```javascript
const words = ["spray", "limit", "elite", "enormous", "destruction", "present"];

const result = words.filter((word) => word.length > 6);

console.log(result); // => ["exuberant","destruction","present"]
```

> [MDN - filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

### Web basics

#### What is a web server?

> 1. On the hardware side, a web server is a computer that stores web server software and a website's component files (e.g. HTML documents, images, CSS stylesheets, and JavaScript files). A web server connects to the Internet and supports physical data interchange with other devices connected to the web.

> 2. On the software side, a web server includes several parts that control how web users access hosted files. At a minimum, this is an *HTTP server*. An HTTP server is a software that understands URLs (web adresses) and HTTP (the protocol your browser uses to view webpages). An HTTP server can be accessed through the domain names of the websites it stores, and it delivers the content of these hosted websites to the end user's device. <br> [MDN - what is a web server?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server#summary)

#### Explain the client-server architecture.

> The Client-server model is a distributed application structure that partitions task or workload between the providers of a resource or service, called servers, and service requesters called clients. In the client-server architecture, when the client computer sends a request for data to the server through the internet, the server accepts the requested process and deliver the data packets requested back to the client. Clients do not share any of their resources. Examples of Client-Server Model are Email, World Wide Web, etc. <br> [Geeks for Geeks - Client-server model](https://www.geeksforgeeks.org/client-server-model/)

#### What is the difference between synchronous and asynchronous execution?

> Synchronous or Synchronized means "connected", or "dependent" in some way. In other words, two synchronous tasks must be aware of one another, and one task must execute in some way that is dependent on the other, such as wait to start until the other task has completed.

> Asynchronous means they are totally independent and neither one must consider the other in any way, either in the initiation or in execution. <br> [Stack Overflow](https://stackoverflow.com/a/748235/19306550)

#### What is `npm`? Why is it useful?

> Node package manager is the world's largest software registry. It's open-source and free to use (no authentication nor login needed). It's installed with Node.js. We can install packages through CLI and we can also publish our own software/package.

#### What is the difference between the `depdendencies` & `devDependencies` in a `package.json` file ?

- "dependencies": Packages required by your application in production.
- "devDependencies": Packages that are only needed for local development and testing. <br> [Geeks for Geeks](https://www.geeksforgeeks.org/difference-between-dependencies-devdependencies-and-peerdependencies/)

#### What would be the impact of javascript `fetch` if it was not asyncronous ?

> It would stall the execution of the code until the fetched resource is not returned.

#### Why benefits would bring to a developer to use the `Postman` application ?

- Helps to design, build, test and iterate APIs
- Provides API repository: Allows users to store, catalog, and collaborate around API artifacts in a central platform within public, private, or partner networks
- Provides API tools: API client, API design, API documentation, API testing, mock servers, and API detection

#### List the parts of the URL.

- protocol (*http*), domain name (third-level ("sub-domain" *www*), second-level (*google*), top-level *com*), port, path, query (*?*), parameters, fragment (*#*) [URL-Anatomy](https://doepud.co.uk/images/complex-url.svg)

#### What is query parameter?

> Query parameters are a defined set of parameters attached to the end of a url. They are extensions of the URL that are used to help define specific content or actions based on the data being passed. To append query params to the end of a URL, a ‘?’ Is added followed immediately by a query parameter. [branch.io](https://branch.io/glossary/query-parameters/)

> A query string is a part of a uniform resource locator (URL) that assigns values to specified parameters. A query string commonly includes fields added to a base URL by a Web browser or other client application, for example as part of an HTML, choosing the appearance of a page, or jumping to positions in multimedia content. [Wikipedia](https://en.wikipedia.org/wiki/Query_string)

#### What kind of HTTP status codes do you know?

> - Informational responses (100 – 199)
> - Successful responses (200 – 299)
> - Redirection messages (300 – 399)
> - Client error responses (400 – 499)
> - Server error responses (500 – 599)

- 100 continue, 101 switching protocolls, 200 OK, 201 created, 204 no content, 300 multiple choices, 301 moved permanently, 400 bad request, 404 not found, 500 internal server error, 502 bad gateway

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?

#### Why should you ignore the `node_modules` folder in `.gitignore` ?

### Rest API: Serve and Fetch

#### Why is it recommend for a developer to use the http methods `get`, `put`, `delete` ?

#### How does a `POST` request look like when it is made from a web browser (on the front end written) ?

#### What is an API?

#### What is REST API?

#### What is JSON and how do we use it?

#### What is API versioning ?

#### Give 3 examples of HTTP response status codes ? Explain what each number means.

### Advanced JavaScript

#### How does the `ternary operator` looks like in javascript?

#### How to import a function from another module in JavaScript?

#### What is a shallow copy on an object?

#### What is a callback function? Tell some examples of its usage.

#### What is object destructuring in javascript?

#### What is array destructuring in javascript?

#### What is the spread operator in `js` ?

#### What are the differences between the `arrow` function and the regular `function`?

#### What is the `import` keyword used for?

#### What is the `required` used for?

#### What are template literals?

### Testing basics

#### What is code coverage? Why is it used?

#### What is a test case? What is an assertion? Give examples!

#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

#### What is arrange/act/assert pattern?

#### How do you test asynchronous code with `jest` ?

#### What is `setup` & `teardown` in jest ?

#### Give an example when you would use in `jest` the `toBe` & `toEqual` assertions.

### React basics

#### What benefits does it bring for a developer to use `components` (opposed of writing all the code in a single file) ?

#### What is the difference between Element and Component?

#### How do you pass values between components in `react`?

#### What is `key` prop?

#### How does a child component pass data to it's parent component ?

#### Write the code to create in JSX an HTML DIV element that has the innerText the contents of the variable `let name = 'Andrew'`

#### Write the code to create in JSX an unordered list from the array `let names = ["Mathew", "John", "Maverik"]`

#### Write the code to set the background color red of a div in JSX.

### Testing react

#### What are unit tests, integration tests? What is the major difference between these two?

#### What is unit testing?

#### What does `mocking` mean from a testing perspective ? Give an example when you would use it.

#### How do you test that function was called `at least` 2 times using `jest` ?

#### Name 4 benefits a developer gets from writing tests.

### React patterns

#### What is the difference between Real DOM and Virtual DOM?

#### When adding an item to an array, why is it necessary to pass a new array to the `useState` hook ?

#### Describe what techniques or tools you use to debug a react app.

#### What is the difference between a react `class` component & a `functional` component ?

#### Name 3 lifecycle states in a react `functional` component.

#### What is conditional rendering in `react` ? Give an example.

#### Write the code that prints to the console `component destroyed` when the component it is part of is removed from the DOM tree.

#### Why is there an infinite loop in this code

```javascript
function App() {
  const [count, setCount] = useState(0); //initial value of this
  useEffect(() => {
    setCount((count) => count + 1); //increment this Hook
  }); //no dependency array.
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```

#### Why is there an infinite loop in this code

```javascript
async function App() {
  const [count, setCount] = useState("");
  setCount(count + 1);
  return (
    <div className="App">
      <p> value of count: {count} </p>
    </div>
  );
}
```

### Mongo & mongoose

#### What is a database schema ?

#### Why is the `id` unique in a database ?

#### What are the advatanges & disadvatages of using `lean()` function in a mongo query ?

#### Write the code to store the object `{name: "Andrew", age: 10}` to a mongo database. You can ignore the part of connection parameters.

#### Write the code to delete from a mongo database all employees that are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.

#### Write the code to display in the console from a mongo database the employees who are over 18 years. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.

#### Write the code to update from a mongo database the employees with name='John' and set the new age to 8. The scheme for an employee is `{name: string, age: int}`. You can ignore the part of connection parameters.

### Authentication (cookies + google)

#### How to properly store passwords?

#### What is encryption and decryption?

#### What is hashing?

#### What is OAuth2?

#### What is the difference between encryption and hashing? When would you use which?

#### How/where would you store sensitive data (like db password, API key, ...) of your application?

#### What would you use a session for?

#### What would you use a cookie for?

### Mern stack

#### What does `MERN` stand for in the context of web development ?

#### What is routing in the context of a `react` app ?

#### What is routing in the context of an `express` app ?

#### What is `CORS` policy ?

#### What advantages does a developer have for using `bootstrap` or `material ui` ?
