Pluralize.swift
===============

Great Swift String Pluralize Extension

- case-insensitive
- tons of rules for irregular nouns (plural form)
- supports uncountable nouns
- allows dynamic addition of rules


Basic usage
-----------
~~~ swift 
"Person".pluralize()
// People

"Wolf".pluralize(count: 1)
// Wolf

"Person".pluralize(with: "Persons")
// Persons
~~~

Examples
-------------------------
| Irregular Nouns          |               | Always Singular in Form   |                  |
| ------------------------ | ------------- | ------------------------- | ---------------- |
| "Amnesty".pluralize()    | Amnesties     | "Coffee".pluralize()      | Coffee           |
| "Dwarf".pluralize()      | Dwarves       | "Compassion".pluralize()  | Compassion       |
| "Hypothesis".pluralize() | Hypotheses    | "Deer".pluralize()        | Deer             |
| "Oasis".pluralize()      | Oases         | "Food".pluralize()        | Food             |
| "Scarf".pluralize()      | Scarves       | "Happiness".pluralize()   | Happiness        |
| "Tableau".pluralize()    | Tableaux      | "Species".pluralize()     | Species          |
| "Vertebra".pluralize()   | Vertebrae     | "Stuff".pluralize()       | Stuff            |

Adding Custom Rules: Singular = Plural
--------------------------------------
~~~ swift
"Shrimp".pluralize()
// Shrimps

Pluralize.unchanging("shrimp")

"Shrimp".pluralize()
// Shrimp
~~~

Adding Custom Rules: Uncountable
--------------------------------
~~~ swift
"Water".pluralize()
// Waters

Pluralize.uncountable("water")
"Water".pluralize()
// Water
~~~

Adding Custom Rules: New Regex Rule
-----------------------------------
~~~ swift
"Person".pluralize()
// People

Pluralize.rule("(p)erson$", with: "$1ersons")
"Person".pluralize()
// Persons
"Spokesperson".pluralize()
// Spokespersons
~~~

Example Regex Rules:
--------------------
~~~ swift
Pluralize.rule("(criteri|phenomen)on$", with:"$1a")
Pluralize.rule("(potat|tomat|volcan)o$", with:"$1oes")
Pluralize.rule("^(|wo|work)man$", with: "$1men")
Pluralize.rule("(f)oot$", with: "$1eet")
Pluralize.rule("lf$", with: "$1lves")
Pluralize.rule("(t)ooth$", with: "$1eeth")
Pluralize.rule("(g)oose$", with: "$1eese")
Pluralize.rule("^(c)hild$", with: "$1hildren")
Pluralize.rule("^(o)x$", with: "$1xen")
~~~


License
-------
Copyright (c) 2014 Joshua Arvin Lat

MIT License

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.