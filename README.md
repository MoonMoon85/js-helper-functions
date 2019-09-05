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
- [Get next sibling which matches a selector](#get-next-sibling-which-matches-a-selector)
- [Get cookie value](#get-cookie-value)
- [Create a query string from object data](#build-a-query-string-from-object-data)
- [Remove duplicates from array](#remove-duplicates-from-array)
- [Format timestamp into a date string](#format-timestamp-into-a-date-string)

## Get next sibling which matches a selector
```javascript
/*!
 * Get next sibling of an element that matches selector
 * @param  {Node}   elem     The element
 * @param  {String} selector The selector to match against
 * @return {Node}            The sibling
 */
var getNextSibling = function (elem, selector) {

	// Get the next sibling element
	var sibling = elem.nextElementSibling;

	// If there's no selector, return the first sibling
	if (!selector) return sibling;

	// If the sibling matches our selector, use it
	// If not, jump to the next sibling and continue the loop
	while (sibling) {
		if (sibling.matches(selector)) return sibling;
		sibling = sibling.nextElementSibling
	}

};
```

## Get cookie value
```javascript
/**
 * Get the value of a cookie
 * @param  {String} name  The name of the cookie
 * @return {String}       The cookie value
 */
var getCookie = function (name) {
	var value = "; " + document.cookie;
	var parts = value.split("; " + name + "=");
	if (parts.length == 2) return parts.pop().split(";").shift();
};
```

## Build a query string from object data
```javascript
/*!
 * Create a query string from object data
 * @param  {Object} data The data to turn into a query string
 * @return {String}      The query string
 */
var createQueryString = function (data) {
	if (typeof (data) === 'string') return data;
	var query = [];
	for (var key in data) {
		if (data.hasOwnProperty(key)) {
			query.push(encodeURIComponent(key) + '=' + encodeURIComponent(data[key]));
		}
	}
	return query.join('&');
};
```

## Remove duplicates from array
```javascript
/*!
 * Remove duplicate items from an array
 * @param  {Array} arr The array
 * @return {Array}     A new array with duplicates removed
 */
var removeDuplicatesInArray = function (arr) {
	return arr.filter(function (item, index) {
		return arr.indexOf(item) === index;
	});
};
```

## Format timestamp into a date string
```javascript
/*!
 * Format timestamp into a date string
 * @param   {String|Integer}  timestamp  The timestamp in unix of YYYY-MM-DD HH:MM:SS format
 * @returns {String}                     A formatted date
 */
var formatDate = function (timestamp) {

	// Create a date object from the timestamp
	var date = new Date(timestamp);

	// Create a list of names for the months
	var months = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October',	'November', 'December'];

	// return a formatted date
	return months[date.getMonth()] + ' ' + date.getDate() + ', ' + date.getFullYear();

};
```
