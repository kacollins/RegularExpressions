# Regular Expressions

# Resources
* Tester https://regex101.com/
* Tester http://regexr.com/
* Tutorial http://www.regular-expressions.info/
* Interactive Tutorial http://regexone.com/
* Puzzles https://regexcrossword.com/

# Notes

Available in many programming languages and text editors
* Useful for developers and power users
* Different syntax in Visual Studio

Easier to write than to read
* Comments are important
* Explain *why* you're doing what you're doing

Write pseudo code first
* Break down the logic
* Think about edge cases

Testing
* List strings that should match
* List similar strings that shouldn't match

Libraries are available online
* Don't reuse without testing
* Add comments if there aren't any

Format
* `/regex/flags`
* Regex is bracketed by slashes

Modifiers (flags)
* `i` Case insensitive
* `g` Global (don't return on first match)
* `m` Multi-line (treat each line as a separate string)

# Examples

Phone numbers
`/\(?\d{3}\)?( |-)?\d{3}( |-)?\d{4}/g`

```
should match:
4055991234
(405) 599-1234
405-599-1234
405 599 1234

should not match:
405599123
40-55991234
```

Words without vowels
`/\b[^aeiouy ]+\b/ig`

```
should match:
Ths is a tst.

should not match:
This is a test.

```

Word characters repeated 3+ times
`/(\w)\1{2}/ig`

```
should match:
teeest
test___test
test000test

should not match:
teest
te e est
```

Repeated words
`/(\b\S+)\s+\1\b/ig`

```
should match:
This is is a test.
This is IS a test.
This isn’t isn’t a test.

should not match:
This is isn’t a test.
```

Two spaces between sentences
`/[.?!] {2,}(?=[A-Z])/g`

```
should match:
This should match.  It has two spaces.
This should match?  It has two spaces.
This should match!  It has two spaces.
This should match.   It has three spaces.

should not match:
This should not match. It only has one space.
This     Should not match.
```

# Other uses
* Finding blocks of commented code
* Replacing text
