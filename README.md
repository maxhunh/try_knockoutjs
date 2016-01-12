# Custom Binding

### Step 1: Define new binding event

Define binding with format:

```javascript
    ko.bindingHandlers.bindingName = {
        // init binding
        // element: elements involved in this binding
        // inValue: `observable` use in binding
        init: function(element, inValue) {
        },
        // update binding (call binding)
        // it not not obligatory
        // change states when binding method be call
        update: function(element, inValue) {
        }
    };
```

### Step 2: Call binding in view

Call binding in view:

```html
    <element data-bind="bindingName: element"></element>
```

### Read more

[Custom binding](http://knockoutjs.com/documentation/custom-bindings.html)