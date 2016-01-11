# Observable

## MVVM and KnockoutJS

### MVVM

MVVM (Model–view–viewmodel) is software architectural pattern. It is a variation of Martin Fowler's **Presentation Model design pattern (Model-View-ViewModel)**. MVVM abstracts a view's state and behavior.  However,  whereas the Presentation Model abstracts a view (i.e., creates a view model) in a manner not dependent on a specific user-interface platform, MVVM was developed specifically to simplify event-driven programming of user interfaces (add layer **Binding**)

![MVVM flow](http://books.zkoss.org/images/f/fb/SmallTalk_MVVM_HELLO_FLOW.png)

**KnockoutJS is Simplify dynamic JavaScript UIs with the Model-View-View Model (MVVM)**

### MVVM in KnockoutJS

Create ViewModel in KnockoutJS

```javascript
    var myViewModel = {
        personName: 'Duc',
        personAge: 321
    };
```

Create simple View for this ViewModel

```html
    The name is <span data-bind="text: personName"></span>
```

Activating KnockoutJS

because `data-bind` isn't HTML's element so to activate Knockout we use

```javascript
    ko.applyBindings(myViewModel);
```


## Observable and how to use this

### Observable

Observable help to UI automatically update when ViewModel update

### How to use observable of KnockoutJS

* Step 1: define observable

Define observable in *ViewModel*:

```javascript
    var myViewModel = {
        // one object
        personName: ko.observable('Duc'),
        personAge: ko.observable(321),
        // multi object
        car = ko.observableArray([
            { name: "BMW", code: "2341" },
            { name: "CBR", code: "4356" },
            { name: "Bike", code: "9999" }
        ]);
    };
```

**Note**: To control *automatic* of observable we can use `subscribe`, `extend`

* Step 2: define function to handle action binding

Define function:

```javascript
    this.findMe = function() {
      // logic need process with this action
    };
```

* Step 3: handle observable

We have just define observable so we want to hanlde action of it. We use *computed*

```javascript
    function AppViewModel() {
        // define object
        this.personName: ko.observable('Duc'),
        this.personAge: ko.observable(321),

        // computed
        this.personInfo = ko.computed(function() {
            return "Name:"+this.personName() + "Age" + this.personAge();
        }, this);
    };
```

Show in view

```html
    Person 's info : <span data-bind="text: fullName"></span>
```

## Reference

* [Wiki](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)
* [Observables](http://knockoutjs.com/documentation/observables.html)
* [Computed](http://knockoutjs.com/documentation/computedObservables.html)

