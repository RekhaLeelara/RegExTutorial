# RegEx Tutorial Email Matching

This tutorial helps to understand one of the frequetly used regular expressions, its function and provide examples.

## Summary

We will use the following regex for our tutorial and the examples provide more insights and better to understand each of the types.
/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

The two anchors given in the Regex are $ and ^. This identifies the position of characters.

^ The code next to this character should appear at the beginning of the string
$ The preceding code should appear at the end of the string

### Quantifiers

Quantifiers helps us to determine the number of times a given character is expected to appear. + and {2,6} are two examples of quantifiers.

[a-z0-9_.-]+, [\da-z.-]+ For these, any character matches the character inside the bracket should appear atleast once 

[a-z.]{2,6} The characters inside the bracket should appear minimum of two times and a maximum of 6 times


### OR Operator

The '|' operator helps to match one of the string. This is not in our example provided.

### Character Classes

A character class allows you to match any symbol from a certain character set. A character class is also called a character set. 

In our expression, \d is used to match any digit character. Also, the a-z will match any character between a and z. 0-9 will match any character between zero and nine. The character class ".", which matches any character, does not require a backslash.


### Flags

A flag is an optional parameter to a regex that modifies its behavior of searching. A flag is denoted using a single lowercase alphabetic character. There are no Flags from our above example but here are some examples

Flag	Name	Modification
i	Ignore Casing	Makes the expression search case-insensitively.
g	Global	Makes the expression search for all occurrences.
s	Dot All	Makes the wild character . match newlines as well.
m	Multiline	Makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string.
y	Sticky	Makes the expression start its searching from the index indicated in its lastIndex property.
u	Unicode	Makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well.

### Grouping and Capturing 
Capturing groups are a way to treat multiple characters as a single unit. They are created by placing the characters to be grouped inside a set of parentheses. Groups use the ( ) symbols (like alternations, but the | symbol is not needed).

Our example has three capturing groups: ([a-z0-9_\.-]+), ([\da-z\.-]+), ([a-z\.]{2,6}). This allows for a substring to be verified before @, another one before \., and the final one for the domain extension of the email address.


### Bracket Expressions

The bracket expressions specify which characters are allowed in a single position of a string. The following three are the examples taken from our Regex. Any character specified within the brackets would be a good match. 

[a-z0-9_.-], [\da-z.-], and [a-z.]

For example, in [a-z0-9_.-], this character will be matched by any lowercase letters from a-z, any digit from 0-9, or a period.


### Greedy and Lazy Match

In the greedy mode, quantifiers try to match as many as possible and return the largest matches. When quantifiers use the greedy mode, they are called greedy quantifiers. In the quantifier tutorial, you learned how to work with greedy quantifiers such as *, +, and ?. Besides the greedy mode, quantifiers also work in the non-greedy mode or lazy mode. In the lazy mode, the quantifiers match their preceding elements as few as possible and return the smallest matches. When quantifiers use the lazy mode, they’re often referred to as non-greedy quantifiers or lazy quantifier

### Boundaries

The (\b) is an anchor like the caret (^) and the dollar sign ($). It matches a position that is called a “word boundary”. The word boundary match is zero-length. We dont have this in our Regex example.

### Look-ahead and Look-behind

Lookarounds will match a group of characters either before or after a pattern, but will allow for it to not be included as part of the result. Lookbehinds are specific for groups that are before the pattern, and lookaheads are for groups after the pattern. We dont have this in our Regex example but see below some common examples.

?=KKK This is a positive lookahead and will match a group after the pattern without including it in the result.
?!RAS This is a negative lookahead and specify a group that cannot match after the pattern; otherwise, the result is unsuccessful.


## Author

Rekha Leelaraman is a current student of Univerity of Toronto bootcamp. Her github profile is 

https://github.com/RekhaLeelara
