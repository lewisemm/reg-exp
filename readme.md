# Regular expression

It's a pattern that can match a piece of text.

The simplest form of regular expression is a plain string (it matches itself) e.g. "Python" will match "Python".

## The wildcard

It's a dot.

Matches any SINGLE character (except a newline).

## Escaping special characters

How do you escape special characters such as the wildcard to represent an actual dot in the patter?

Use the backslash (you may need to use two of them if the backslash character itself has special meaning).

## Character sets

You can create a character set by enclosing a substring into brackets.

Character sets vary a single character in a string independently.

e.g. [pj]ython means the letter 'p' or 'j' are the only possible options for the first letter.
This means a match can only be made for two strings i.e. 'python' and 'jython'

Character sets allow you to use ranges for well known sequences e.g. [a-z] instead of writing all the letters of the alphabet => [abcd..xyz]

Common ranges include;
  * [a-z] lowecase range, [A-Z] uppercase range
  * [0-9] integers

Ranges can even be combined inside a character set e.g. [a-zA-Z0-9] is valid.

In our previous [py]thon example, if we wanted to expand the character set of the first letter so that it matches any letter of the alphabet, we could use [a-z]ython.

This would create matches for aython, bython, cython, dython ... zython

Character sets can also be used as inverts i.e. to match any character other than the ones in the brackets.

We do this by including a caret (^) as the first character in the character set e.g. [^pj]ython will match every combination listed above except 'python' and 'jython'

## Alternatives and subpatterns
Sometimes you may want to match entire patterns instead of single characters.

Alternatives could help you do this.

We use the pipe (|) character for alternatives.

To match the strings "python" and "perl", the pattern would be "python"|"perl"

Still, sometimes you don't want to use the alternative operator on entire patterns; just a part of it.

This is where subpatterns come in.

Subpattern are enclosed in parenthesis.

The previous example could be re-written as p(ython|erl)