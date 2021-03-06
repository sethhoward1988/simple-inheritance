Simple-Inheritance
==================

Class.js is a simple method for writing fully extensible JavaScript classes.

#How It Works

Class.js is 41 lines of code that takes in a hash of attributes and methods as well as the class that is being extended, if any. Below is a sample of how to create a class using Class.js.


 ```javascript
Reptile = Class({

	initialize: function () {
		console.log('Creating a reptile');
	},

	setSkinColor: function (color) {
		this.skinColor = color;
	},

	getSkinColor: function () {
		return this.skinColor;
	}

});
 ```

 This has now created the class Reptile to the window. Typing `Reptile` into the command line would return the constructor. `Reptile.prototype` shows all methods shown above.

###Extending a Class

```javascript
Gecko = Class({

	initialize: function () {
		console.log('Creating a Gecko');
	},

	setLength: function (length) {
		this.length = length;
	},

	getLength: function () {
		return this.length;
	}

}, Reptile);
```

There are now Gecko and Reptile classes on the window. `myGecko = new Gecko()` will return a new Gecko. `myGecko.super` returns the constructor for the super class (Reptile) and `myGecko.super.prototype` are all the parent methods.

###Extending Multiple Classes

To continue extending more than one class, follow the pattern above and only pass in the class which is being extended. A chain is formed and the super methods are appended to each class as it's being created. Modifying any method on the prototype chain will alter it for all classes. For example, the code to extend Gecko again is shown below.

```javascript
GeckoSpecies = Class({}, Gecko);
```

###Warning

JavaScript was not created to have deep inheritance like classical languages. This code imitates that type of inheritance. Checking class inheritance by using `instanceof` is not reliable.

###Comments

Since this is one of the first few open souce projects I'm working on, feel free to comment on the code or methods. I'm always open to criticism.
