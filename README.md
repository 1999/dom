## What is this?
DOM sugar for new browsers. JS DOM manipulation library for modern (Chrome 5+, Firefox 3.6+, IE9+) browsers with a jQuery-like chainable syntax.

## How does it work?
DOM creates a mixin in the prototype chains of the HTMLElements and NodeLists. After this you can access all methods of DOM in context of the current node/list at the same time with using the native DOM elements' stuff like "appendChild", "addEventListener" etc.

Also the library provides a more convenient and simplier [window.$](#window-and-window-api) and [window.$$](#window-and-window-api) methods to replace querySelector and querySelectorAll methods.

## HTMLElement's extended API
```javascript
/**
 * Find closest ancestor node
 * @param {String} selector
 * @return {HTMLElement|Null}
 */
closestParent: function (selector) {},

/**
 * Bind event listener to node
 * @param {String} evtType
 * @param {Function} callback
 * @param {Boolean} singleton
 * @return {HTMLElement} refers to this
 */
bind: function (evtType, callback, singleton) {},

/**
 * Remove node
 * @return {HTMLElement} refers to this
 */
remove: function () {},

/**
 * Get innerHTML property of a node or set it
 * @param {String|Undefined} newHTML
 * @return {HTMLElement|String} innerHTML or node which refers to this
 */
html: function (newHTML) {},

/**
 * Get textContent property of a node or set it
 * @param {String|Undefined} newContent
 * @return {HTMLElement|String} textContent or node which refers to this
 */
text: function (newContent) {},

/**
 * Empty innerHTML of a node
 * @type {HTMLElement} refers to this
 */
empty: function () {},

/**
 * Append HTML code, HTMLElement or NodeList to a node
 * @param {String|HTMLElement|NodeList} contents
 * @return {HTMLElement} refers to this
 */
append: function (contents) {},

/**
 * Insert HTML code, HTMLElement or NodeList to the beginning of a node contents
 * @param {String|HTMLElement|NodeList} contents
 * @return {HTMLElement} refers to this
 */
prepend: function (contents) {},

/**
 * Insert HTML code, HTMLElement or NodeList before a node
 * @param {String|HTMLElement|NodeList} contents
 * @return {HTMLElement} refers to this
 */
before: function (contents) {},

/**
 * Insert HTML code, HTMLElement or NodeList after a node
 * @param {String|HTMLElement|NodeList} contents
 * @return {HTMLElement} refers to this
 */
after: function (contents) {},

/**
 * Get value of a node or set it
 * @param {Mixed|Undefined} newValue
 * @return {HTMLElement|Mixed} node value or node which refers to this
 */
val: function (newValue) {},

/**
 * Add one or mutiple classes to a node classList
 * @param [arguments] classNames
 * @return {HTMLElement} refers to this
 */
addClass: function () {},

/**
 * Remove one or mutiple classes from a node classList. If arguments count is 0, than classList is cleared
 * @param [arguments] classNames
 * @return {HTMLElement} refers to this
 */
removeClass: function () {},

/**
 * Check whether one or all of the classes are in the classList property of a node
 * @param [arguments] classNames
 * @return {Boolean}
 */
hasClass: function () {},

/**
 * Toggle the existence of a class in an element's list of classes
 * @type {Boolean}
 */
toggleClass: function (className, force) {},

/**
 * Get attribute(s) of a node or set it
 * @param {String} key
 * @param {Mixed} value
 * @return {HTMLElement} refers to this
 *
 * or
 * @param {Object} key-value map of the attributes
 * @return {HTMLElement} refers to this
 *
 * or
 * @param {String} key
 * @return {Mixed} attribute's value
 */
attr: function (key, value) {},

/**
 * Remove node's attribute
 * @return {HTMLElement} refers to this
 */
removeAttr: function (key) {},

/**
 * Get dataset value(s) or set it
 * @param {String} key
 * @param {Mixed} value
 * @return {HTMLElement} refers to this
 *
 * or
 * @param {Object} key-value map of the dataset
 * @return {HTMLElement} refers to this
 *
 * or
 * @param {String} key
 * @return {Mixed} attribute's value
 */
data: function (key, value) {},

/**
 * Delete dataset properties from a node. If arguments count is 0, than dataset of a node will be cleared
 * @param [arguments] dataset keys
 * @return {HTMLElement} refers to this
 */
removeData: function () {},

/**
 * Get style property value(s) of a node or set it
 * @param {String} key
 * @param {Mixed} value
 * @return {HTMLElement} refers to this
 *
 * or
 * @param {Object} key-value map of the dataset
 * @return {HTMLElement} refers to this
 *
 * or
 * @param {String} key
 * @return {Mixed} attribute's value
 */
css: function (key, value) {}
```

## NodeList's extended API
```javascript
/**
 * Apply callback to each element of the list
 * @param {Function} callback where this refers to parsed element of the list
 * @return {NodeList} refers to this
 */
each: function (callback) {},

/**
 * Bind event listener to every element of the list
 * @param {String} evtType
 * @param {Function} callback
 * @param {Boolean} singleton
 * @return {NodeList} refers to this
 */
bind: function (evtType, callback, singleton) {},

/**
 * Empty innerHTML properties of every element in the list
 * @return {NodeList} refers to this
 */
empty: function () {},

/**
 * Remove every element of the list from their parents
 * @return {NodeList} refers to this
 */
remove: function () {},

/**
 * Add one or mutiple classes to every element's classList
 * @param [arguments] classNames
 * @return {NodeList} refers to this
 */
addClass: function () {},

/**
 * Remove one or mutiple classes from every element's classList. If arguments count is 0, than classList is cleared
 * @return {NodeList} refers to this
 */
removeClass: function () {}
```

## window.$ and window.$$ API
```javascript
/**
 * Shortened and more convenient "querySelector"
 * @return {HTMLElement|Null}
 * @throws {TypeError} if arguments are invalid
 *
 * @example
 * $(document.body) returns a document body itself
 * $("<div>smth</div>") returns a new div element with innerHTML property set to "smth"
 * $("div.wrapper p") returns the same as document.querySelector("div.wrapper p")
 * $(parentNode, "p") returns the same as parentNode.querySelector("p")
 */
window.$ = function () {},

/**
 * Shortened and more convenient "querySelectorAll"
 * @return {NodeList}
 * @throws {TypeError} if arguments are invalid
 *
 * @example
 * $$(nodeList) returns a nodeList itself
 * $$("div.wrapper p") returns the same as document.querySelectorAll("div.wrapper p")
 * $$(parentNode, "p") returns the same as parentNode.querySelectorAll("p")
 */
window.$$ = function () {}
```
## License
[Apache License, Version 2.0](https://github.com/1999/dom/blob/master/LICENSE)
