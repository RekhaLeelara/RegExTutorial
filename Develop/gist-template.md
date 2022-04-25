# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

A regular expression is a string which matches the pattern. You can search and replace the strings using RegEx effectively. For example, if you want to convert the phone number format from xxx-xx-xxxx to xxxxxxxxx, regEx would be handy. Another example, if you want to replace Hello! with Hola! in 1000 places, RegEx is very useful. We will see some of the RegEx and examples in the following pages.

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
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors do not match any character. Instead, they match a position before or after characters

Ex: The following example returns true as the string ends with 't'

let str = 'JavaScript';
console.log(/t$/.test(str));

### Quantifiers
Quantifiers match a number of instances of a character, group, or character class in a string

Ex: For example, to find numbers that have two, three, or four digits, you use the regular expression /\d{2,4}/g. The following example returns a output of (34, 2023)

let str = 'The official name of ES34 is ES2023';
let re = /\d{2,4}/g;

let result = str.match(re);
console.log(result);

Quantifier	Description
*	Match zero or more times.
+	Match one or more times.
?	Match zero or one time.
{ n }	Match exactly n times.
{ n ,}	Match at least n times.
{ n , m }	Match from n to m times.

### OR Operator

The '|' operator helps to match one of the string. Please see the following examples


"hi|hello"

matches a string that has either "hi" or "hello" in it

"(b|cd)ef"

a string that has either "bef" or "cdef"

"(a|b)*c"

a string that has a sequence of alternating a's and b's ending in a c

### Character Classes
A character class allows you to match any symbol from a certain character set. A character class is also called a character set.

Ex: If you want change the phone number format to just numbers. You just use the following code and the output of this code is 14085550105.

let phone = '+1-(408)-555-0105';
let re = /\d/g;

let numbers = phone.match(re);
let phoneNo = numbers.join('');

console.log(phoneNo);

### Flags

### Grouping and Capturing
Capturing groups are a way to treat multiple characters as a single unit. They are created by placing the characters to be grouped inside a set of parentheses. Groups use the ( ) symbols (like alternations, but the | symbol is not needed). They are useful for creating blocks of patterns, so you can apply repetitions or other modifiers to them as a whole. In the pattern ([a-x]{3}[0-9])+, the + metacharacter is applied to the whole group. Some of the sample groups given below:

Parantheses Group: (regex) Parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.

Example: (abc){3} matches abcabcabc. First group matches abc.

Escaped parentheses group: Escaped parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.

Example: \(abc\){3} matches abcabcabc. First group matches abc.

### Bracket Expressions

The bracket expressions specify which characters are allowed in a single position of a string. Some of the examples given below:

"[ab]"

matches a string that has either an a or a b (that's the same as "a|b")

"[a-d]"

a string that has lowercase letters 'a' through 'd' (that's equal to "a|b|c|d" and even "[abcd]")

"^[a-zA-Z]"

a string that starts with a letter

"[0-9]%"

a string that has a single digit before a percent sign

",[a-zA-Z0- 9]$"

a string that ends in a comma followed by an alphanumeric character

### Greedy and Lazy Match

In the greedy mode, quantifiers try to match as many as possible and return the largest matches. When quantifiers use the greedy mode, they are called greedy quantifiers. In the quantifier tutorial, you learned how to work with greedy quantifiers such as *, +, and ?.

Besides the greedy mode, quantifiers also work in the non-greedy mode or lazy mode. In the lazy mode, the quantifiers match their preceding elements as few as possible and return the smallest matches. When quantifiers use the lazy mode, they’re often referred to as non-greedy quantifiers or lazy quantifiers.

Greedy quantifier	Lazy quantifier	Meaning
*	*?	Match its preceding element zero or more times.
+	+?	Match its preceding element one or more times.
?	??	Match its preceding element zero or one time.
{ n }	{ n }?	Match its preceding element exactly n times.
{ n ,}	{ n ,}?	Match its preceding element at least n times.
{ n , m }	{ n , m }?	Match its preceding element from n to m times.

Example: The following program uses the non-greedy quantifier (+?) to match the text within the quotes ("") of a button element. The output of the following example is ['"submit"', '"btn"']

const s = '<button type="submit" class="btn">Send</button>'
const pattern = /".+?"/g;

const result = s.match(pattern)
console.log(result);

### Boundaries

The (\b) is an anchor like the caret (^) and the dollar sign ($). It matches a position that is called a “word boundary”. The word boundary match is zero-length.

The following three positions are qualified as word boundaries:

Before the first character in a string if the first character is a word character.
After the last character in a string if the last character is a word character.
Between two characters in a string if one is a word character and the other is not.

Example: The output for the following example is "JS"

console.log('Hello, JS!'.match(/\bJS\b/));

### Back-references
Backreferences allow you to reference the capturing groups in the regular expressions. Technically speaking, backreferences are like variables in regular expressions. The syntax of a backreference is \N

Example: The output for the below example is "JavaScript is cool" as we removed the duplicate JavaScript word from the sentence.

const s = 'JavaScript JavaScript is cool';
const pattern = /(\w+)\s+\1/;

const result = s.replace(pattern, '$1');

console.log(result);

### Look-ahead and Look-behind

Generic Look-ahead:

In regular expressions, a lookahead allows you to match X but only if it is followed by Y. The syntax of the lookahead is X(?=Y)

Example: The output for the following code is 15. The following code uses the above pattern to match the number that is followed by zero or more spaces and the literal string feet.

const s = '1 car is 15 feet long';
const pattern = /\d+(?=\s*feet)/;

const match = s.match(pattern);
console.log(match);

Negative Look-ahead: If you want to match just the '1' and not the '15' then you use negative Look-ahead. The syntax of the lookahead is X(?!Y).

Example: The output for the following program is '1'

const s = '1 car is 15 feet long';
const pattern = /\d+(?!\s*feet)/;

const match = s.match(pattern);
console.log(match);

Generic Look-behind:

In regular expressions, a lookbehind matches an element if there is another specific element before it. The syntax is (?<=Y)X

Example: The output for the following code is '[ '900', index: 18, input: '1 computer costs $900', groups: undefined ]'. The following example illustrates how to use a lookbehind in a regular expression to match a number that has the $ sign before it.

const s = '1 computer costs $900';
const pattern = /(?<=\$)\d+/;

const match = s.match(pattern);
console.log(match);

Negative Look-ahead: To negate a lookbehind, you use a negative lookbehind with the syntax '(?<!Y)X'

Example: The output for the following program is '1'

const s = '1 computer costs $900';
const pattern = /(?<!\$)\d+/;

const match = s.match(pattern);
console.log(match);

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
