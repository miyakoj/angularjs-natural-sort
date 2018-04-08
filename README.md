AngularJS Natural Sort Comparator
=======

Description
---------------
Based on [javascript-natural-sort](https://github.com/overset/javascript-natural-sort) by Jim Palmer, AngularJS Natural Sort is an orderBy filter comparator that sorts simple arrays and arrays of objects in "natural" order. All strings are compared case-insensitively.

**Note:** There is also a plain JavaScript function available: [https://github.com/miyakoj/javascript-natural-multisort](https://github.com/miyakoj/javascript-natural-multisort)

Installation
---------------
Copy and paste the code in natural-sort.js into your app.

Usage
---------------
```javascript
{{ collection | orderBy : expression : reverse : naturalSort }}
ng-repeat="ngRepeat_expression | orderBy : expression : reverse : naturalSort"
ng-options="ngOptions_expression | orderBy : expression : reverse : naturalSort"
$filter('orderBy')(collection, expression, reverse, $scope.naturalSort)
```

### Notes
* In order to use "track by", it must be added after the "orderBy" filter.
* To sort a simple array with no objects, use an empty string for the expression; otherwise, use the property you want to sort on.
* Reverse is either true for reverse sorting or false for regular sorting.
* The comparator is on the main scope, but it doesn't have to be. See this [Pen](https://codepen.io/miyakoj/pen/WzZrMe) for an example.


Examples
---------------

#### Original Simple Array:
```javascript
['p1', 'p5', 'p10', 'p25', 'p2']
```

#### AngularJS default comparator
```javascript
['p1', 'p10', 'p2', 'p25', 'p5']
```

#### The naturalSort comparator
```javascript
['p1', 'p2', 'p5', 'p10', 'p25']
```
------------------
#### Original Array of Objects:
```javascript
[
    {name: "p1", number: 1},
    {name: "p5", number: 5},
    {name: "p10", number: 10},
    {name: "p25", number: 25},
    {name: "p2", number: 2}
]
```

#### AngularJS default comparator (sorting on "name")
```javascript
[
    {name: "p1", number: 1},
    {name: "p10", number: 10},
    {name: "p2", number: 2},
    {name: "p25", number: 25},
    {name: "p5", number: 5}
]
```

#### The naturalSort comparator (sorting on "name")
```javascript
[
    {name: "p1", number: 1},
    {name: "p2", number: 2},
    {name: "p5", number: 5},
    {name: "p10", number: 10},
    {name: "p25", number: 25}
]
```