# Hata

Lightweight JavaScript framework for manipulation dom elements.

### Table of content:
* [Getting started](#getting-started)
* [Manipulation with dom elements](#manipulation-with-dom-elements)
  * [Constructor](#constructor)
  * [Select one element](#select-one-element)
  * [Get plain non-wrapped DOM nodes](#get-plain-non-wrapped-dom-nodes)
  * [Iterations](#iterations)
  * [Filter elements](#filter-elements)
  * [Closest element](#closest-element)
* [Invoking code after DOM is fully loaded](#invoking-code-after-dom-is-fully-loaded)
* [Extending](#extending)
* [Applications use hata](#applications-use-hata)
* [Contributions](#contributions)

## Getting started

Writing is in progress.

## Manipulation with dom elements

### Constructor:
```js
var elements = hata( selector [, context ]);
```

`selector` and `context` can be string selector, hata object or node.

### Select one element:
```js
elements.eq( number ); // => Hata object of one element
```
`number` can be positive or negative number.


### Get plain non-wrapped DOM nodes:
```js
elements.get(); // => Array of nodes
elements.get( number ); // => One node by index
```
`number` can be positive or negative number.

### Iterations:
```js
elements.each(fucntion( element, index ) {
  // this => node element
  // element => node element
  // index => index of node element
});
```
This method return elements.

### Filter elements:
```js
elments.filter( selector ); // => Hata object of elements filtering by `selector`
```
`selector` can be string selector, hata object or node.

### Closest element:
```js
elments.closest( selector ); // => First parents by `selector` or this elements if it is `selector`
```
`selector` can be string selector, hata object or node.

## Invoking code after DOM is fully loaded
```js
hata.ready(function() {
  // Invoks when dom is ready
});
```

## Extending
If you want to extend hata methods:
```js
hata.extend( hata.fn, {
  ping: function() {
    return 'pong';
  }
});

// or

hata.fn.ping = function() {
  return 'pong';
}

elements.ping(); // => 'pong'
```

If you want to extend some objects:
```js
var someObject = {};

hata.extend( someObject, {
  ping: function() {
    return 'pong';
  }
});

someObject.ping(); // => 'pong'
```

## Applications use hata

* [vkleaner](http://vkleaner.losky.net) - chrome extension for vk.com that hides unwanted posts. Look at [sources](https://github.com/EvgenyZhlobo/vkleaner/tree/master/js) for better understand role of Hata.

## Contributions

Contribuitions always are welcome. Hata is written according to [jQuery Core Style Guide](http://docs.jquery.com/JQuery_Core_Style_Guidelines) and:
```js
// Good
if ( condition ) return some;
if ( condition ) break;
```
Feel free to fork and pull request changes.
