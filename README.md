# Dart for JavaScript developers

<hr />

## Table of Contents

- [Dart for JavaScript developers](#dart-for-javascript-developers)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting Started](#getting-started)
    - [install Dart](#install-dart)
    - [run your first dart app](#run-your-first-dart-app)
  - [Comments](#comments)
  - [Data Types](#data-types)
    - [Integers (`int`)](#integers-int)
    - [Doubles (`double`)](#doubles-double)
    - [Strings (`String`)](#strings-string)
    - [Booleans (`bool`)](#booleans-bool)
    - [Dynamic (`dynamic`)](#dynamic-dynamic)
  - [Constants](#constants)
  - [Control Flow (`if`, `for`, `while`, `switch`)](#control-flow-if-for-while-switch)
    - [`if` statement](#if-statement)
    - [`for` loop](#for-loop)
    - [`while` loop](#while-loop)
    - [`switch` statement](#switch-statement)
  - [conditional expressions](#conditional-expressions)
    - [ternary operator](#ternary-operator)
    - [null-aware operators](#null-aware-operators)
  - [Collections](#collections)
    - [Lists](#lists)
      - [List methods](#list-methods)
        - [`add()`](#add)
        - [`addAll()`](#addall)
        - [`insert()`](#insert)
        - [`insertAll()`](#insertall)
        - [`remove()`](#remove)
        - [`removeAt()`](#removeat)
        - [`removeLast()`](#removelast)
    - [Maps](#maps)
      - [Map methods](#map-methods)
        - [`putIfAbsent()`](#putifabsent)
        - [`addAll()`](#addall-1)
        - [`remove()`](#remove-1)

## Introduction

This is a quick guide to help JavaScript developers get started with Dart, as well as a reference for the differences between Dart and JavaScript.

## Getting Started

### install Dart

Dart is available for Windows, Mac, and Linux. You can download the SDK from the [Dart website](https://dart.dev/get-dart), follow the [installation instructions](https://dart.dev/get-dart#install), and then run the `dart` command from the command line.

### run your first dart app

after installing the dart SDK you can now start running dart in your local machine

Create a new file called `hello.dart` with the following contents:

```dart
main() {
  print('Hello, World!');
}
```

> Note: The `main()` function is the entry point for all Dart apps.
>
> the `print()` function in the equivalent of `console.log()` in JavaScript

Run the app from the command line:

```bash
dart hello.dart
```

You should see the following output:

```bash
Hello, World!
```

[Back to Table of Contents](#table-of-contents)

## Comments

Dart supports single-line and multi-line comments.

Single-line comments start with two forward slashes (`//`):

```dart
// this is a single-line comment
```

multi-line comments start with a forward slash followed by an asterisk (`/*`) and end with an asterisk followed by a forward slash (`*/`):

```dart
/*
  this is a multi-line comment
  we can use it to define a paragraph
*/
```

[Back to Table of Contents](#table-of-contents)

## Data Types

Dart is a strongly typed language, which means that all variables have a specific type. Dart supports the following data types:

| Type      | Description                                     |
| --------- | ----------------------------------------------- |
| `int`     | 64-bit (signed) two's complement integer        |
| `double`  | 64-bit double-precision floating point number   |
| `String`  | Sequence of characters                          |
| `bool`    | Boolean value (`true` or `false`)               |
| `dynamic` | this means that the variable can be of any type |

[Back to Table of Contents](#table-of-contents)

### Integers (`int`)

Integers are whole numbers, positive or negative, without decimals. Here are some examples of defining integer literals:

```dart
var age = 25;
var hex = 0xDEADBEEF;
```

### Doubles (`double`)

If a number includes a decimal, it is a double. Here are some examples of defining double literals:

```dart
var amount = 25.5;
var exponents = 1.42e5;
```

Note: we declare variables using the `var` keyword, this is the equivalent of `let` in JavaScript, and it specifies the type of the variable from the initialization value.
we can also strongly type the variable by using the type name before the variable name, for example:

```dart
int age = 25;
double amount = 25.5;
```

> Note: Both `int` and `double` are subtypes of `num`, which means that they are both considered numbers.

You can also use the `num` type to define a variable that can be either an integer or a double:

```dart
num age = 25;
age = 25.5;
```

### Strings (`String`)

There are various ways to define a string literal in Dart. Here are some examples:

```dart
String myName = 'charaf';
String myName = "charaf";
// we can escape characters using \
String weather = 'it\'s sunny';
// we can use triple quotes to define multi-line strings
String multiLine = '''
  this is a multi-line string
  we can use it to define a paragraph
''';
String anotherMultiLine = """
  this is another multi-line string
  we can use it to define a paragraph
""";
```

> Note: you can add variables to a string using the `$` symbol, similar to string literals in JavaScript

```dart
String myName = 'charaf';
print('my name is $myName');
// you can also use ${} to add expressions
int price = 10;
double tax = 0.3;
print('the total price is ${price + price * tax}');
```

### Booleans (`bool`)

Booleans are either `true` or `false`. Here are some examples of defining boolean literals:

```dart
var isTrue = true;
bool isFalse = false;
```

### Dynamic (`dynamic`)

The `dynamic` type means that the variable can be of any type. Here are some examples of defining dynamic literals:

```dart
int age = 25;
age = 'charaf'; // this is not valid and will throw an error

dynamic name = 'charaf';
name = 25; // this is valid
```

[Back to Table of Contents](#table-of-contents)

## Constants

similar to javascript, constants are values that cannot be changed once they are defined. In Dart, you can define constants using the`const` keyword.

```dart
const PI = 3.14;
const double G = 9.8;
```

> Note: you can also define constants using the `final` keyword, but the difference is that you can only assign a value to a `final` variable once, and after that you cannot change it.

```dart
final PI = 3.14;
final double G = 9.8;
```

[Back to Table of Contents](#table-of-contents)

## Control Flow (`if`, `for`, `while`, `switch`)

### `if` statement

similar to Javascript declaration of conditions, we can use the `if` statement to execute a block of code if a condition is true.

```dart
int age = 25;
if (age > 18) {
  print('you are an adult');
}
```

we can also use the `else` keyword to execute a block of code if the condition is false.

```dart
int age = 15;
if (age > 18) {
  print('you are an adult');
} else {
  print('you are a child');
}
```

we can also use the `else if` keyword to add more conditions.

```dart
int age = 15;
if (age > 18) {
  print('you are an adult');
} else if (age > 12) {
  print('you are a teenager');
} else {
  print('you are a child');
}
```

### `for` loop

I'm happy to tell you that it's the same syntax and behavior as Javascript, so you don't need to learn anything new.

```dart
for (int i = 0; i < 5; i++) {
  print(i);
}
```

> Note: you can use `break` and `continue` keywords to break or continue the loop.

```dart
for (int i = 0; i < 5; i++) {
  if (i == 3) {
    break;
  }
  print(i);
}
```

```dart
// print only odd numbers
for(int i = 0; i < 10; i++) {
  if (i % 2 == 0) {
    continue;
  }
  print(i);
}
```

we can also use the `for in` loop to iterate over a collection.

```dart
var array = [1, 2, 3, 4, 5];
for (var item in array) {
  print(item); // 1, 2, 3, 4, 5
}
```

you can also use `forEach` on Lists to iterate over them.

```dart
var array = [1, 2, 3, 4, 5];
array.forEach((item) => print(item)); // 1, 2, 3, 4, 5
```

> Note: Yep .. I see .. forEach uses an arrow function .. told ya it's the same as Javascript 😁
>
> we will see functions and data structures later

### `while` loop

similar to Javascript, we can use the `while` loop to execute a block of code as long as a condition is true.

```dart
int i = 0;
while (i < 5) {
  print(i);
  i++;
}
```

dart also supports the `do while` loop, which is similar to Javascript.

```dart
int i = 0;
do {
  print(i);
  i++;
} while (i < 5);
```

### `switch` statement

similar to Javascript, we can use the `switch` statement to execute a block of code based on a condition.

```dart
int age = 25;
switch (age) {
  case 18:
    print('you are an adult');
    break;
  case 12:
    print('you are a teenager');
    break;
  default:
    print('you are a child');
}
```

[Back to Table of Contents](#table-of-contents)

## conditional expressions

### ternary operator

we can use the `?` and `:` operators to define a conditional expression.

```dart
int age = 25;
String message = age > 18 ? 'you are an adult' : 'you are a child';
print(message);
```

the above code is equivalent to:

```dart
int age = 25;
String message;
if (age > 18) {
  message = 'you are an adult';
} else {
  message = 'you are a child';
}
print(message);
```

### null-aware operators

we can use the `??` operator to assign a default value to a variable if it's null.

```dart
var name = null;
String message = name ?? 'you have no name';
print(message);
```

this is used in cases where we want to assign a default value to a variable if it's null.

there are cases where we need to take the value of a property in an object and assign it to a variable but sometimes the property is not 100% exist so we need a default value instead of null.

```dart
class Person {
  String name;
}

main() {
  Person person = Person();
  int age = person.age; // this will throw an error because the age property doesn't exist
}
```

to prevent that error from happening, there is an operator that we use in javascript as well as in dart which is the `?.` operator.

```dart
class Person {
  String name;
}

main() {
  Person person = Person();
  int age = person?.age; // this will return null if the age property doesn't exist
}
```

we can also use the `??` operator to assign a default value to the variable if the property doesn't exist.

```dart
class Person {
  String name;
}

main() {
  Person person = Person();
  int age = person?.age ?? 0; // this will return 0 if the age property doesn't exist
}
```

[Back to Table of Contents](#table-of-contents)

## Collections

### Lists

Arrays in javascript are called Lists in dart.

```dart
var array = [1, 2, 3, 4, 5];
```

we can strictly define the type of the elements in the list by using the `List` class.

```dart
List<int> array = [1, 2, 3, 4, 5];
List<String> names = ['Ahmed', 'Mohamed', 'Ali'];
// List is the type of the variable
// <int> used to define the type of the elements in the list
```

if we don't define the type of the elements in the list, the list will be dynamic and we can add any type of elements to it.

```dart
var array = [1.5, 2, true, null, 'charaf'];
```

> Dart will throw an error if you try to add an element of a different type to a list that has a defined type.

```dart
List<int> array = [1, 'charaf']; // this will throw an error
```

Similar to Javascript, Lists are non-premitive data structures, so they are passed by reference, for more on that subject in javascript check [this article](https://cmarghin.hashnode.dev/javascript-understanding-stack-heap-and-the-difference-between-them)

```dart
var array = [1, 2, 3, 4, 5];
var array2 = array;

array2.add(6); // I changed in the second array, but the first one will also be changed

print(array); // [1, 2, 3, 4, 5, 6]
```

Dart also supports the **spread operator** which is the same as Javascript.

```dart
var array = [1, 2, 3, 4, 5];
var array2 = [6, 7, 8, 9, 10];

var array3 = [...array, ...array2];

print(array3); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

#### List methods

##### `add()`

we can use the `add()` method to add an element to the end of the list. equivalent to `push()` in javascript.

```dart
var array = [1, 2, 3, 4, 5];
array.add(6);

print(array); // [1, 2, 3, 4, 5, 6]
```

##### `addAll()`

we can use the `addAll()` method to add a list of elements to the end of the list. equivalent to `concat()` in javascript.

```dart
var array = [1, 2, 3, 4, 5];
array.addAll([6, 7, 8, 9, 10]);

print(array); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

##### `insert()`

we can use the `insert()` method to add an element to a specific index in the list.

```dart
var array = [1, 2, 3, 4, 5];
array.insert(2, 6); // add 6 at index 2

print(array); // [1, 2, 6, 3, 4, 5]
```

##### `insertAll()`

we can use the `insertAll()` method to add a list of elements to a specific index in the list.

```dart
var array = [1, 2, 3, 4, 5];
array.insertAll(2, [6, 7, 8, 9, 10]); // add [6, 7, 8, 9, 10] at index 2

print(array); // [1, 2, 6, 7, 8, 9, 10, 3, 4, 5]
```

##### `remove()`

we can use the `remove()` method to remove an element from the list.

```dart
var array = [1, 2, 3, 4, 5];
array.remove(3);

print(array); // [1, 2, 4, 5]
```

##### `removeAt()`

we can use the `removeAt()` method to remove an element from a specific index in the list.

```dart
var array = [1, 2, 3, 4, 5];
array.removeAt(2);

print(array); // [1, 2, 4, 5]
```

##### `removeLast()`

we can use the `removeLast()` method to remove the last element from the list. equivalent to `pop()` in javascript.

```dart
var array = [1, 2, 3, 4, 5];
var k = array.removeLast();

print(array); // [1, 2, 3, 4]
print(k); // 5
```

for more details about the `List` class, check [this link](https://api.dart.dev/stable/2.18.6/dart-core/List-class.html)

[Back to Table of Contents](#table-of-contents)

### Maps

Maps are key-value pairs data structures in dart, similar to `Map` in javascript.

```dart
var object = {
  'name': 'Ahmed',
  'age': 25,
};
```

you can also declare it using the `Map` class.

```dart
Map<String, dynamic> object = {
  'name': 'Ahmed',
  'age': 25,
};
// Map is the type of the variable
// <String, dynamic> used to define the type of the keys and values in the map
```

> Note: the keys in map can be of any type, for example, we can use numbers and booleans as keys.

```dart
var object = {
  1: 'Ahmed',
  true: 'Mohamed',
  1.6: 'Ali',
};
```

> Note: unlike Javascript, you can't use dot notation to access the value of a key in a map, you have to use the `[]` notation.

```dart
var object = {
  'name': 'Ahmed',
  'age': 25,
};

print(object.name); // this will throw an error
print(object['name']); // Ahmed
```

#### Map methods

##### `putIfAbsent()`

we can use the `putIfAbsent()` method to add a key-value pair to the map if the key doesn't exist. it takes two parameters, the first one is the key, and the second one is a function that returns the value of the key.

```dart
var object = {
  'name': 'Ahmed',
  'age': 25,
};

object.putIfAbsent('new', () => 'yesss');
object.putIfAbsent('name', () => 'Mohamed');

print(object); // {name: Ahmed, age: 25, new: yesss}
```

##### `addAll()`

we can use the `addAll()` method to add a map of key-value pairs to the map.

```dart
var object = {
  'name': 'Ahmed',
  'age': 25,
};

object.addAll({'new': 'yesss', 'name': 'Charaf'});
print(object); // {name: Charaf, age: 25, new: yesss}
```

##### `remove()`

we can use the `remove()` method to remove a key-value pair from the map.

```dart
var object = {
  'name': 'Ahmed',
  'age': 25,
};

object.remove('name');
print(object); // {age: 25}
```

for more details about the `Map` class, check [this link](https://api.dart.dev/stable/2.18.6/dart-core/Map-class.html)
