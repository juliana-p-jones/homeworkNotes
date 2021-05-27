NOTES:
-part 1 = callbacks/promises/RxJs/async await (academind)
-part 2 = typescript tutorial (Derek Banas)
-part 3 = how the web works (academind)
-part 4 = Understanding Event Loops article (Digital Ocean)
-part 5 = How the Web Works ARTICLE (MDN WebDocs)


CallBacks vs Promises vs RxJs Observables vs async/ await


In synchronous operations tasks are performed one at a time and only when one is completed, the following is unblocked. In other words, you need to wait for a task to finish to move to the next one. In asynchronous operations, on the other hand, you can move to another task before the previous one finishes.


CallBacks:
Oldest way of working with data once it’s there and continueing execution of the other code while the async code is executing

In video example:
Button called “fetch User” when pressed: -> “Checking authority…” -> “Fetching user…” -> “Max”
-he has checking and fetching set to timers
-at the bottom he has an event listener function

the event listener button only happens when the timer functions happen
cb = callback
callback’s can get really messy with error testing! They can get nested terribly

Promises:
Promises are classes which promise a certain value in the future.
new Promise = how to make a new promise..

if you return a promise in a ‘then block’, you can chain another ‘then block’ to the end, instead of nesting

RxJs:
Rx.Observable.create(
)

Promises handle ONE value, Observables can handle STREAMS of data- that’s the difference between a one time hit button vs something that is listening to a flow of clicks on screen to make events happen

Its more difficult to learn, but handling streams of data and having a lot of operators make RxJs better

Async/Await:
New feature
Looks like synchronous code- one thing happening after the other (easy to read!)
async has to go in front of your function definition, this will signal everything inside may use the await keyword to pause the JS execution

await is the keyword of wait for this promise
// await fetchUser()

===================================================================================
Banas Typescript Video Notes:

Make a buncha variables:
var myName: string = “Derek;
var myAge: number = 41;
var canVote: Boolean = true;
var anything: any = “dog”;
anything = 2;

if you don’t specify the data type it will be inferred.

Link TS doc up to HTML:
Add this to <body> tag in html doc:
<script src = “tstut.js”></script>
<p id=”tsStuff”></p>

in TS doc
doc.getElementById(“tsStuff)
.innerHTML = “my name is “ + myName;

document.write(“myname is a ” + typeof(myName) + “<br/>”);
document.write(“myname is a ” + typeof(canVote) + “<br/>”);
document.write(“myname is a ” + typeof(anything) + “<br/>”);

var strToNum: number = parseInt(“5”);
//parses to a string
var numbToStr: number = 5;
document.write(“numToStr is a “ + typeof(numbToStr.toString()) + “<br/>”);
const PI = 3.1349

//typeof prints the type of things

“Complex Data Types” Example:
interface SuperHero {
realName: String;
superName: String;
}

var superman: SuperHero = {
realName: “Clark Kent”,
superName: “Superman”
}
document.write(superman.realName + “ is “ + superman.superName + “<br />”)
// prints: Clark Kent is Superman
// you can use dot operator to find the key value pairs essentially

To Create Array of Strings
var employees: string[] = [“Bob”, “Sally”, “Sam”];
employees.push(5); //DOES NOT WORK because 5 is a num not a string!
document.write(employees.toString() + “<br />);
//prints: Bob,Sally,Sam

interface SuperHero {
realName: String;
superName: String;
}

var superheroes: SuperHero[] = [];

superheroes.push({
realName: ‘Bruce Wayne’,
superName:’Batman’
});

document.write(superheroes[0].realName + “ is “ + superheroes[0].superName + “<br />”);
//[0] to get that first element
// prints: Bruce Wayne is Batman

MATH
 document.write(“5 + 4 = “ + (5+4) + “ <br />”); //prints: 5 + 4 = 9
document.write(“5 - 4 = “ + (5-4) + “ <br />”);//prints: 5 – 4 = 1
document.write(“5 * 4 = “ + (5*4) + “ <br />”);//prints: 5 * 4 = 20
document.write(“5 / 4 = “ + (5/4) + “ <br />”);//prints: 5 / 4 = 1.25
document.write(“5 % 4 = “ + (5%4) + “ <br />”);//prints: 5 % 4 = 1

document.write(“5 + String 2 = “ + (5+’2’) + <br />”); //prints 5 + String 2 = 52

var randNum: number = 1;


Increment ++ and Decrement -- is tricky:
randNum = randNum + 1

document.write(“randNum++ = ” + randNum++ + “<br />”); //prnt: randNum++ = 1
document.write(“++randNum = ” + ++randNum + “<br />”);//prnt: ++randNum = 3
document.write(“randNum-- = ” + randNum-- + “<br />”);//prints: randNum-- = 3
document.write(“--randNum = ” + --randNum + “<br />”);//prints: --randNum =1

//whenever you print the incr/decr at the end it will be ignored, if its put first it will increment/decrement first
//randNum = randNum + 1 is the same as randNum++
//the state of the number is being stored each time

If Switch and Ternary Operator:
let sampLet = 123;

if(true){
let sample = 456;
}

document.write(“sampLet: “ +sampLet + “<br />”); //prints sampLet: 123

var sampVar = 123;
if(true){
var sampLet = 456;
}
document.write(“sampLet: “ +sampLet + “<br />”); //prints sampLet: 123

if you use let you can’t change the value inside a conditional statement, but you can with var.

Making Arrays:
var randArray= [5,6,7,8];
for(var val in randArray){
document.write(val + “<br />”); //prints 0 1 2 3 on separate lines
}

var strArray = randArray.map(String);
for(var val of strArray){
document.write(val + “<br />”); // prints 5 6 7 8 on separate lines
}


Making Functions
Declare it function, in parenthesis are the params, after is the return type
var getSum= function(num1: number, num2: number): number{
return num1 + num2;
}

var theSum1: number= getSum(5,2);
document.write(“5+2 = “ + theSum1 + “<br />”); // prints 5 + 2 = 7

var getDiff =  function(num1: number, num2: 2, num3?: number): number{


if(typeof num3 !== ‘undefined’){
return num1- num2 –num3;
}
return num1 – num2;
}
document.write(“5 - 2=” + getDiff(5) + “<br />”); // 5 – 2 =3
document.write(“5 – 2 - 3=” + getDiff(5,2,3) + “<br />”); // 5 – 2 – 3 = 0


var sumAll = function(…nums: number[]): 
void{
var sum = nums.reduce((a,b) => a + b, 0);

document.write(“Sum : “ + sum + “<br />”);

}
sumAll(1,2,3,4,5); // Sum : 15

Arrow Function:
 var addOne = (x) => x+1;
document.write(“1+1 = “ + addOne(1) + <br />”); // 1 + 1 = 2


Making Classes
class Animal{
public favFood: string; //public means you can change the value easily
static numOfAnimals: number = 0;
constructor(private name: string, private owner: string){
Animal.numOfAnimals++;
}
ownerInfo(){
document.write(this.name + “ is owned by “ + this.owner + “<br />”);
}
static howManyAnimals():number{
return Animal.numOfAnimals;
}
private _weight: number;
get weight(): number{
return this._weight;
}

set weight(weight: number){
this._weight = weight;
}

var spot = new Animal(“Spot”, “Doug”);
spot.ownerIfo(); //Spot is owned by Doug

spot.weight = 100; //SETS THE WEIGHT! Don’t have to write set

doc.write(“# of Animals: “  + Animal.howManyAnimals() + “<br/>”); // # of Animals: 1
}

class Dog extends Animal{
constructor(name: string, owner: string){
super(name, owner)
Dog.numOfAnimals++;
}
}

var grover = new Dog(“Grover”, “Jimmy”);

doc.write(“# of Anima;s : “ + Animal.howManyAnimals() + <br>); # of animals : 2

doc.write(“Is Dog an Animal : “ + (grover instanceof Animal) + <br>);// is dog an animal : true
doc write(“Does grover have a name: “ + (‘name’ in grover + <br>); // does grover have a name : true
//when there are statements inside parenthesis like: (grover instanceof Animal) TS evaluates that statement as a Boolean

Interface:
Interface Vehicle{
Drive():any;
}

class Car implements Vehicle{
constructor(private wheels: number){}
drive(): void{
doc.write(“the car drives with” + this.wheels + “ wheels” “<br / >”);
}
}

class Bicycle implements Vehicle{
constructor(private wheels: number){}

drive(): void{
doc.write()” this bicycle drives with” + this.wheels + “ wheels<br />”);
}
}
var car = new Car(4);
var bike = new Bicycle(2);

car.drive();// car drives with 4 wheels
bike.drive(); // bike drives with 2 wheels

Generic Functions:

function GetType<t>(val: T): string{
return typeof(val);
}

var aStr = “A String”;
var aNum = 10;
doc.write(GetType(aStr) + “<br />”); // string
doc.write(GetType(aNum) + “<br />”);// number

//function can handle any data types

//////back to the bike/car example//////

var car = new Car(4);
var bike = new Bicycle(2);

function GetWheels<w extends Vehicle>(veh: 1): number{
return veh.drive();
}

GetWheels(car);
GetWheels(bike);

Generic Classes: 

class GenericNumber<T>{
add: (val1: T, val2: T) => T;
}

var aNumber = new GenericNumber<number>();
aNumber.add = function(x,y){return x + y;};

document.write(“5 + 4 = “ + aNumber.add(5, 4) + “<br />”); // 5 + 4 = 10

var aStrNum = new GenericNumber<string>();
aStrNum.add = function(x,y){return String(Number(x) + Number(y));};

document.write(“5 + 6 = “ + aStrNum.add(5, 6) + “<br />”); // 5 +6 =11


var randVals = {x: 1, y: 2, z: 3};
var{x,y,z} = randVals;
document.write(x + y+ z”<br/>”;)//123
[x,y,z] = [z,y,x]; //super easy to flip an array
doc.write(“Switch: “ + x + y + z “<br/>”);// 321

multistring:
var multStr= `I go on for many lines<br/>`;
docwrite(multStr); // I go on for many lines
docwrite(`<b>${multStr}<b>`); // I go on for many lines /// IN BOLD///


Spread Operator
function theSum(x,y,z): void{
doc.write(“Sum : “ + (x+Y+Z) + “<br />”);
}
var args = [4,5,6];
theSum(…args); //15

Numerated Types:
Enum Emotion{
Happy = 1,
Sad,
Angry
}
var myFeeling = Emotion.Happy
myFeeling = 1;	

============================================================================

How the Web Works:

Website is stored on a server
Browser is an interpreter that gets back certain source vode that can be dsiplayed on our screen
How does the server know what we mean when we look up a certain url?

IP = Internet Protocol ---- its the one with a bunch of numbers and decimals

The first thing that happens is our browser contacts a DNS Server where each domain name is mapped to an IP
DNS = Domain Name Server
Then the DNS translates the domain into an IP address which is given to the browser, which can be given to the server which is reaching the actual website

Browsers make request
request is a package of data that has a type (GET, storing data), might include data or not! might include meta data

What you get back is a Response
the Html code comes back and is displayed, which is what we are familir with when we look at websites

HTML = hypertext markup language. gives website structure
CSS = Cascading Style Sheets. gives the website style
JavaScript = the logic and dynamic things that happen in the browser (tabs, drop down menus, everything that changes in the page after it has been downloaded

HTTP = hypertext transfer protocol
HTTPS = hypertext transfer protocol secure (end to end encrypted)

With mobile apps, you aren't getting HTML back but just data...
it gets JSON data back
basically there is more to the web than just html/css/javascript- its the transfer of data in many forms

============================================================================

Digital Ocean Understanding the Event Loop Notes:

JavaScript's a single-threaded programming language with a synchronous execution model that processes one operation after another

Blocking is when the browser cannot handle any user unput until a synchronous operation is complete

Event Loop is the OG way of dealing with asynchronous behavior

Stack: The stack, or call stack, holds the state of what function is currently running.
Last in first Off! Think stack of pancakes

Queue: a waiting area for functions, aka the british word for line

Callback Functions: Callback functions do not have special syntax; they are just a function that has been passed as an argument to another function
Callbacks are not asynchronous by nature but can be used for nefarious asynchronous purposes

callback hell: wow i thought that guy was joking. don't nest callbacks, it gets too messy for testing software

Promises: It is an object that might return a value in the future
initialize a promise with the "new Promise" syntax
All promises have resolve and reject parameters in the passed down function

for example:
// Initialize a promise
const promise = new Promise((resolve, reject) => {})

A promise can have three possible states: pending, fulfilled, and rejected.

Pending - Initial state before being resolved or rejected
Fulfilled - Successful operation, promise has resolved
Rejected - Failed operation, promise has rejected
After being fulfilled or rejected, a promise is settled.

Handing errors with promises:
then(): Handles a resolve. Returns a promise, and calls onFulfilled function asynchronously
catch(): Handles a reject. Returns a promise, and calls onRejected function asynchronously
finally(): Called when a promise is settled. Returns a promise, and calls onFinally function asynchronously

Asyn Functions with async/await:
More traditional javascript syntax- looks pretty synchronous save a few key words
// Create an async function
async function getUser() {
  return {}
}
// Handle fetch with async/await
async function getUser() {
  const response = await fetch('https://api.github.com/users/octocat')
  const data = await response.json()

  console.log(data)
}

// Execute async function
getUser()
// Handling success and errors with async/await
async function getUser() {
  try {
    // Handle success in try
    const response = await fetch('https://api.github.com/users/octocat')
    const data = await response.json()

    console.log(data)
  } catch (error) {
    // Handle error in catch
    console.error(error)
  }
  ============================================================================
  How the Web Works ARTICLE (MDN WebDocs) Notes:

  computers connected to the web are called clients and servers. Clients make requests, servers provide responses

  Servers are computers that store webpages, sites, or apps

TCP/IP: Transmission Control Protocol and Internet Protocol
----communication protocols that define how data should travel across the internet.

Component files: made up of mainly two types...
    
    Code files: Websites are built primarily from HTML, CSS, and JavaScript, though you'll meet other technologies a bit later.

    Assets: This is a collective name for all the other stuff that makes up a website, such as images, music, video, Word documents, and PDFs.

DNS make IP addresses possible- how else would we be able to memorize or put in those long strings of numbers accurately??

Packets: when data is sent across the web it is sent in small chunks
This is efficient because if something goes wrong, like a packet is dropped or corrupted it isn't a LARGE amount of data lost, and its big enough it cna still be speedy without being cumbersomely large and slowing people down with long download speeds

1. browser goes to DNS server, finds the real IP address
2. browser sends an HTTP request message to the server, sent using TCP/IP
3.if the server approves the request, sends client back a response message and starts sending a series of data packets to the clinet
4. browser assembles the small chunks into a whole webpage which is displaayed for us