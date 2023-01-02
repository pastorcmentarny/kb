# DEFINITION

Regex is a regular expression is a sequence of characters defining a search pattern.

Regex works on characters, not words. Concatenation is implied.

* The . (dot) character matches any single character. - c.t we would match anything ranging from cat to c0t or cAt
* The * (asterisk) character is a bit more difficult. It modifies the character preceding it and then matches zero or
  more characters of that. Yes, read that again, zero or more characters. For example, cat* would match cat, catt,
  cattttt but also ca.
* The ^ (caret) fixes your pattern to the beginning of the line. For example the pattern ^1 matches any line starting
  with a 1.
* The $ (dollar) fixes your pattern to the end of the sentence. For example, 9$ matches any line ending with a 9.
* Character sets are like [0..9] or *
* The * (asterisk) is a modifier. A modifier changes the meaning of the character preceding it.

## Examples:

* ```(^.*) $1,```
* ```(.+?\()``` match everything until ( and then \U$1\E to replace with upper case
* ```.*(55).*```
* ```^.*\b(CONTENT)\b.*$``` Select everything before CONTENT and everything after
* ```.*(50|51|52|53|54|55|56|57|58|59).*```
* ```REGEX remove blank lines: ^(?:[\t ]*(?:\r?\n|\r))+```
