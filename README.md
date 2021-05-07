# Javascript-Methods
A list of javascript methods

# Array Methods 

## Splice - O(n)
Changes the contents of an array by removing or replacing existing elements and/or adding new elements in place

let fruits = [ "Banana", "Orange", "Apple", "Mango" ];
fruits.splice(2, 0, "Lemon", "Kiwi");  = Banana, Orange, Lemon, Kiwi, Apple, Mango
	
## Map - 0(n)
Loops through every element of an array and applies a function to each, creating new array

const gardnerGang = [
    {name: 'Brian', age: 20},
    {name: 'Dashlin', age: 26},
    {name:'Tanecia', age: 30}
];

const userDescriptions = users.map(item => {
   return `Hello my name is ${item.name} and I’m ${item.age} years old.`
});

console.log(userDescriptions); 
/*["Hello my name is Brian and I’m 20 years old.",
 "Hello my name is Dashlin and I’m 26 years old.",
 "Hello my name is Tanecia and I’m 30 years old."] */


## Reduce - 0(n)
Loop and run a function on each element of the array, resulting in a single output value.
const team = [
  {name:'Brian', age:20},
  {name:'Tanecia', age:30},
  {name:'Ziya', age:22}
];

const reducer= (accumulator, item)=> accumulator + item.age;
const totalAge =  team.reduce( reducer, 0 );
const ageAverage = totalAge / team.length;
console.log(`Total ${totalAge}, Average ${ageAverage}`); // Total 72, Average 24


## Filter - 0(n)
Creates a new array with all elements that pass the test implemented by the provided function.

Const gardnerGang = [ “Dashlin”, “Asianna”, “Tanecia”, “Wade”, “Brian”, “Julie”]
Const coolPeople = gardnerGang.filter( name => name.length > 4);
console.log(coolPeople) ; 
	[“Dashlin”, “Asianna”, “Tanecia”, “Brian”, “Julie”]
________________________________________________________________

const users = [
  {name:'Asianna', admin: true},
  {name:'Ziya', admin: true},
  {name:'Wade'}
];
const adminUsers =  users.filter (item => item.admin);
console.log(adminUsers); // [{name: "Asianna", admin: true},{name: "Ziya", admin: true}]


## forEach - 0(n)
Loops through an array and runs a function once for each element 
function sumMix(array){  
  let sum = 0;
  array.forEach((numberOrString) => {
    sum = Number(numberOrString) + sum
  })
  return sum
}


## Sort - 0(n * log(n)) - quasilinear - iterations that use divide and conquer
Sorts the elements of an array in order and returns the newly organized array

const names = ['Dash','Brian','Asianna','Tanecia', “Wade”];
console.log( names.sort( ) ); // (4) ["Asianna", "Brian", "Dash", "Tanecia", “Wade”]

/*complex sorting*/
const users = [
    {name:'Dash', age:26},
    {name:'Brian', age:20},
    {name:'Asianna', age:30}
];


const compare = ( item1,item2 ) => {
  return item1.age - item2.age;
};
console.log( users.sort( compare ));
/**
 [{name: "Brian", age: 20}, {name: "Dash", age: 26}, {name: "Asianna", age:30}]
 */


## Slice - 0(n)
Returns a copy of a portion of an array into a new array object selected from start to end. If an end is not specified, it’s assumed it’s to the end of the array. The original array isn’t changed.

const animals = [ 'ant', 'bison', 'camel', 'duck', 'elephant' ];

console.log( animals.slice( 2 ) );
// expected output: Array ["camel", "duck", "elephant"]

console.log( animals.slice( 2, 4 ) );
// expected output: Array ["camel", "duck"]

console.log( animals.slice( 1, 5 ) );
// expected output: Array ["bison", "camel", "duck", "elephant"]

## Pop - 0(1) - constant
Method ‘pops’ an element off the end of an array

const names = [ 'Dashlin','Brian','Asianna','Tanecia'];
console.log( names.pop( ) ); //Tanecia
console.log(names); // (3) ['Dashlin','Brian','Asianna']



## Shift - 0(n)
Method removes an element from the beginning 
const names = ['Dash','Wade,'Brian','Ziya'];
console.log(names.shift()); // Dash
console.log(names); // (3) ["Wade", "Brian", "Ziya"]

## Push - 0(1) - constant
Method adds an element to the end of an array

const names = [ 'Dashlin' , 'Wade' ,'Brian'];
names.push('Gardner Baby');
console.log(names) =  // (4) ['Dashlin' , 'Wade' ,'Brian', 'Gardner Baby']

## Unshift - 0(n)
Method adds an element to the beginning of an array

const names = ['Dash','Brian,'Kev'];
console.log( names.unshift ( "Monica" ) ); // 4
console.log(names); // (4) ["Monica", "Dash", "Brian", "Kevin"]

## Includes - 0(n)
Returns true or false if an array includes a certain element.

function getCount(str) {
  let vowelsCount = 0;
  const vowel = ["a", "e", "i", "o", "u"]
  
  for( let letter of str.toLowerCase( ) ){
    If ( vowel.includes ( letter )){
      vowelsCount++
    }
  }
    return vowelsCount;
}


## indexOf - 0(n)
Returns the first index at which a given element can be found in the array, or -1 if it is not present.
const names = ['Davida','Asianna','Monica','Kevin'];
console.log( names.indexOf ( "Monica" )); // 2
console.log(names.indexOf("Jeon")); // -1


## Every - 0(n)
Loop like forEach but tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

const maxRcAge= (gardnerAge) => gardnerAge < 32;
const array1 = [20, 20, 25, 26, 30, 30];
console.log( array1.every( maxRcAge ));
// expected output: true

# String Methods 

## charAt
The charAt() method returns the character at the specified index in a string.
const sentence = 'The quick brown fox jumps over the lazy dog.';

const index = 4;

console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// expected output: "The character at index 4 is q"



## charCodeAt - O(1)
returns an integer between 0 and 65535 representing the UTF-16 code unit at the given index.

## Concat - O(n)
merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array = array1.concat(array2);

console.log(array3);
// expected output: Array ["a", "b", "c", "d", "e", "f"]


## Includes
Determines whether an array includes a certain value among its entries, returning true or false as appropriate.

const array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true


## indexOf
returns the index within the calling String. Returns -1 if the value is not found.

const paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';

const searchTerm = 'dog';
const indexOfFirst = paragraph.indexOf(searchTerm);

console.log(`The index of the first "${searchTerm}" from the beginning is ${indexOfFirst}`);
// expected output: "The index of the first "dog" from the beginning is 40"

console.log(`The index of the 2nd "${searchTerm}" is ${paragraph.indexOf(searchTerm, (indexOfFirst + 1))}`);
// expected output: "The index of the 2nd "dog" is 52"


## Repeat
Returns a new string with a specified number of copies of the strings concatenated together.

const repeated = 'I love mimi. ';

console.log(`My brain brain on repeat: ${ repeated.repeat(10) }`);

// expected output: "My brain brain on repeat: I love mimi. I love mimi. I love mimi. I love mimi. I love mimi. I love mimi. I love mimi. I love mimi. I love mimi. I love mimi.


## Replace
Replaces an element in a string
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replace('dog', 'monkey'));
// expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"

## Slice
extracts a section of a string and returns it as a new string, without modifying the original string.
const str = 'The quick brown fox jumps over the lazy dog.';

console.log(str.slice(31));
// expected output: "the lazy dog."

console.log(str.slice(4, 19));
// expected output: "quick brown fox"

console.log(str.slice(-4));
// expected output: "dog.”
console.log(str.slice(-9, -5));
// expected output: "lazy"

## Split - O(n)
divides a String into an ordered list of substrings, puts these substrings into an array, and returns the array.  The division is done by searching for a pattern; where the pattern is provided as the first parameter in the method's call. 

	const str = 'The quick brown fox jumps over the lazy dog.';

const words = str.split(' ');
console.log(words[3]);
// expected output: "fox"

const chars = str.split('');
console.log(chars[8]);
// expected output: "k"

const strCopy = str.split();
console.log(strCopy);
// expected output: Array ["The quick brown fox jumps over the lazy dog."]


## Substr
returns a portion of the string, starting at a specified index and extending for a given number of characters afterwards.

const str = 'Mozilla';

console.log(str.substr(1, 2));
// expected output: "oz"

console.log(str.substr(2));
// expected output: "zilla"


## toLowerCase - 0(n)
Turns all the letters of the string into lowercase
	const sentence = 'The quick brown fox jumps over the lazy dog.';

console.log(sentence.toLowerCase());
// expected output: "the quick brown fox jumps over the lazy dog."



## toUpperCase
Turns all the letters of the string into uppercase

  const sentence = 'The quick brown fox jumps over the lazy dog.';

  console.log(sentence.toUpperCase());
  // expected output: "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG."



## Trim
 Method removes whitespace from both ends of a string.
  const greeting = '   Hello world!   ';

  console.log(greeting);
  // expected output: "   Hello world!   ";

  console.log(greeting.trim( ));
  // expected output: "Hello world!";


## Match
Retrieves the result of matching a string against a regular expression.



## Search
searches a string for a specified value, and returns the position of the match.



