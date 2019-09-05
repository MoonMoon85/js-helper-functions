# Javascript Helper functions
Helper functions to leverage and help make repeating tasks easier.

_By [Will Shalders](http://willshalders.me)_

These Javascript helper functions come in handy when doing repeatative tasks and help make your code DRY.

Currently I use these to help write A/B tests and upload most of them to the testing tool of choice. These should then be made available via a module which is then made available in the global scope.

## Example of how to use
```javascript

/*!
 * Revealing helper functions following the module pattern
 */
var helpers = (function () {

	'use strict';

	//
	// Variables
	//

	var publicHelpers = {};


	//
	// Methods
	//

	/**
	* A public method
	*/
	publicHelpers.doSomething = function () {
		// Code goes here...
	};


	//
	// Return the Public Methods
	//

	return publicHelpers;

})();
```

## Helper Functions
- [Purpose](#purpose)

## Example of how to use
```javascript

/*!
 * Revealing helper functions following the module pattern
 */
var helpers = (function () {

	'use strict';

	//
	// Variables
	//

	var publicHelpers = {};


	//
	// Methods
	//

	/**
	* A public method
	*/
	publicHelpers.doSomething = function () {
		// Code goes here...
	};


	//
	// Return the Public Methods
	//

	return publicHelpers;

})();
```
## Example of how to use
```javascript

/*!
 * Revealing helper functions following the module pattern
 */
var helpers = (function () {

	'use strict';

	//
	// Variables
	//

	var publicHelpers = {};


	//
	// Methods
	//

	/**
	* A public method
	*/
	publicHelpers.doSomething = function () {
		// Code goes here...
	};


	//
	// Return the Public Methods
	//

	return publicHelpers;

})();
```

## Purpose
