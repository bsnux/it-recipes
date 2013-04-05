JavaScript OOP
===============

# Creating objects

There are many ways of creating objects in JavaScript:

## Using new Object()

	person = new Object()
	person.name = "Tim Scarfe"
	person.height = "6Ft"

	person.run = function() {
		this.state = "running"
		this.speed = "4ms^-1"
	}

## Literal notation

	timObject = {
		property1 : "Hello",
		property2 : "MmmMMm",
		property3 : ["mmm", 2, 3, 6, "kkk"],
		method1 : function(){alert("Method had been called" + this.property1)}
	};

	timObject.method1();

# Objects and constructor

	/* Constructor */
	function Person(gender) {
	  this.gender = gender;
	  console.log('Person instantiated');
	}

	/* Prototype-based */
	Person.prototype.sayHello = function()
	{
	  console.log ('hello');
	};

	var person1 = new Person('Male');
	var person2 = new Person('Female');

	// call the Person sayHello method.
	person1.sayHello(); // hello

# Methods

In JavaScript methods are regular function objects that are bound to a class/object
as a property which means they can be invoked "out of the context". Consider the following example code:

	function Person(gender) {
	  this.gender = gender;
	}

	Person.prototype.sayGender = function()
	{
	  console.log(this.gender);
	};

	var person1 = new Person('Male');
	var genderTeller = person1.sayGender;

	person1.sayGender(); // console.logs 'Male'
	genderTeller(); // console.logs undefined
	console.log(genderTeller === person1.sayGender); // console.logs true
	console.log(genderTeller === Person.prototype.sayGender); // console.logs true

This example demonstrates many concepts at once. It shows that there are no
"per-object methods" in JavaScript since all references to the method point to
the exact same function, the one we have defined in the first place on the prototype.
JavaScript "binds" the current "object context" to the special "this" variable when
a function is invoked as a method(or property to be exact) of an object.

# Inheritance

In the example below, we define the class **Student** as a child class of **Person**.
Then we redefine the **sayHello()** method and add the **sayGoodBye()** method.


	// define the Person Class
	function Person() {}

	Person.prototype.walk = function(){
	  console.log ('I am walking!');
	};
	Person.prototype.sayHello = function(){
	  console.log ('hello');
	};

	// define the Student class
	function Student() {
	  // Call the parent constructor
	  Person.call(this);
	}

	// inherit Person
	Student.prototype = new Person();

	// correct the constructor pointer because it points to Person
	Student.prototype.constructor = Student;

	// replace the sayHello method
	Student.prototype.sayHello = function(){
	  console.log('hi, I am a student');
	}

	// add sayGoodBye method
	Student.prototype.sayGoodBye = function(){
	  console.log('goodBye');
	}

	var student1 = new Student();
	student1.sayHello();
	student1.walk();
	student1.sayGoodBye();

	// check inheritance
	console.log(student1 instanceof Person); // true
	console.log(student1 instanceof Student); // true