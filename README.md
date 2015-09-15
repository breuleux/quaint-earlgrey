
quaint-earlgrey
===============

Allows inline Earl Grey code in Quaint markup.

Expressions in curly brackets will be evaluated using Earl Grey's
interpreter.

Usage:

```javascript
var quaint = require("quaint");
var qeg = require("quaint-earlgrey");

var q = quaint(qeg);

q.toHTML("2 + 3 = {2 + 3}")
// ==> "2 + 3 = 5"
```

In Earl Grey code, you can use the `%` operator to create HTML
elements programmatically:

```javascript
q.toHTML("{a[.cls][#id] % [href = 'there', 'A', 'B']}")
'<a href="there" id="id" class="cls">AB</a>'

q.toHTML("{1..3 each i -> b % i * i}")
// ==> "<b>1</b><b>4</b><b>9</b>"
```
