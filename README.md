# Compoment

### Init compoment with knockoutjs

```javascript
    ko.components.register('name-components', {
        viewModel: function(params) {
            // Handle action of this components
        },
        template:
            '<!-- html code of this component -->'
    });
```

### Use component in view

```html
     <name-components params="value: inputVal"></name-components>
```

### Read more:

[Compoment](http://knockoutjs.com/documentation/component-overview.html)