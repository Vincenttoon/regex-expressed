# Email Regex Explained

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

- This gist will provide a breakdown of the email validation regex, why and how it works for other developers to understand and share.

## Summary

- An email validation Regex is an excellent way to ensure users of an application are filling out the email field properly so the application can use that information and function properly. This public gist will explain the different components of this regex so the reader and future developers can better understand how it works.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy Match](#greedy-match)

## Regex Components

- Email Validation Regex:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Anchors

- `^`

  - Signifies the start of string and what will be accepted through the regex parameters

- `$`
  - Signifies the end of the string the regex is effecting

### Quantifiers

- Quantifiers match a number of instances of a character or group in a string. There are 2 different quantifiers in this regex, identified by `{}` and `+`

Quantifier 1:
`{`2,6`}`

- This quantifier requires the previous regex requirements to be between 2 and 6 characters in order to work within the applications parameters.

Quantifiers 2 & 3:
([a-z0-9_\.-] `+` ) / ([\da-z\.-] `+` )

- The `+` quantifier is shorthand to accept one digit of the previous parameters in order to work within the application parameters.

### Character Classes

- Character classes allow the user to insert a set of specific characters that matches the approved regex requirements

  - `a-z0-9_\.-`

- This character class allows the user to insert letters a-z, 0-9, underscore(\_), then followed by a period(.) or a hyphen(-)

  - `\da-z\.-`

- The \d is looking for any single character that is a digit, letter, and followed by a . or a -

  - `a-z\.`

- Must return any letter follow by a period

### Grouping and Capturing

- These groups are determined by calling parenthesis `()` and then follows the regex instructions for user insertion inside. There are three captured groups in this regex:

Group 1:

- `(` [a-z0-9_\.-]+ `)`

Group 2:

- `(` [\da-z\.-]+ `)`

Group 3

- `(` [a-z\.]{2,6} `)`

### Bracket Expressions

- Bracket Expressions are the `[]` containers that home the character classes and what parameters need to be followed for both the user and the application to receive their desired result. There are three bracket expressions in this regex:

B.E. 1:

- `[` a-z0-9\_\.- `]`

B.E. 2:

- `[` \da-z\.- `]`

B.E. 3:

- `[` a-z\. `]`

### Greedy Match

- When a match is greedy, it tries to extract as much possible information from it's assigned expression until it conforms to a pattern that would have been sufficient shorter. This allows for the accepting of multiple different lengths and variations of expression as long as it meets the desired criteria.

- The `+` Quantifier is inherently greedy, which means this regex example contains two greedy matches. See [Quantifiers](#quantifiers) for the `+` quantifier/greedy match examples.

    - There are lazy matches, which repeats the first token as few times as possible. An example would look like `+?` (instead of `+`). Further explanation would be available in a separate, more relevant example.

## Author

This Gist was written by Vincent Toon, a full-stack MERN developer while attending 2U's Bootcamp through Washington University. For more information about myself or to view other projects I am currently/have worked on, please visit my github:

- [Vincent Toon's Github](https://github.com/Vincenttoon)
