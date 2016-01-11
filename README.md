# Binding

## Define to use KnockoutJS

* Step 1: define data-binding

Define binding in html element with format `<element data-bind="type binding: action"></element>`

Ex: `<button data-bind="click: findMe" >Find Me !</button>`


* Step 2: define main function

Define function follow format:

```javascript
    var handleClick = function() {
      // code to handle binding action
    };
    ko.applyBindings(new handleClick());
```


* Step 3: define function to handle action binding

Define function:

```javascript
    this.findMe = function() {
      // logic need process with this action
    };
```

## Read more:

* [Binding document](http://knockoutjs.com/documentation/introduction.html)

