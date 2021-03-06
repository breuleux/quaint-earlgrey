
quaint-earlgrey
===============

Allows inline
[Earl Grey](http://earl-grey.io)
code in
[Quaint](http://breuleux.github.io/quaint)
markup.

Allows inline Earl Grey code in Quaint markup.

Expressions in curly brackets will be evaluated using Earl Grey's
interpreter.


## Install

    quaint --setup earlgrey


## Usage

```
2 + 2 is {2 + 2}
```

### API

#### JavaScript

```javascript
var quaint = require("quaint");
var qeg = require("quaint-earlgrey");

var q = quaint(qeg);

q.toHTML("2 + 3 = {2 + 3}");
// ==> "2 + 3 = 5"
```

#### Earl Grey

```earlgrey
require: quaint, quaint-earlgrey as qeg

q = quaint(qeg)

q.toHTML("2 + 3 = {2 + 3}")
// ==> "2 + 3 = 5"
```

## Functionality

In embedded Earl Grey, you can use the `%` operator to create HTML
elements programmatically.

```javascript
q.toHTML("{a[.cls][#id] % [href = 'there', 'A', 'B']}");
// ==> '<a href="there" id="id" class="cls">AB</a>'

q.toHTML("{1..3 each i -> b % i * i}");
// ==> "<b>1</b><b>4</b><b>9</b>"
```

Some additional documentation [here](http://earl-grey.io/doc.html#documentbuildingsyntax)


## Options

### `sandbox`

An object to use as the global object for `eval`. All the properties
you set on that object will be available as top level variables in
scripts.

