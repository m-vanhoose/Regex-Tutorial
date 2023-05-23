# Regular Expressions

This document is a tutorial to explain the usage and individual parts of the expression ``(?=^.{8,}$)(?=.*\d)(?=.*[!@#$%^&*]+)(?![.\n])(?=.*[A-Z])(?=.*[a-z]).*$`` as well as what the components in the expression are doing.

## Summary

The regex ``(?=^.{8,}$)(?=.*\d)(?=.*[!@#$%^&*]+)(?![.\n])(?=.*[A-Z])(?=.*[a-z]).*$`` is used check the complexity of a user's password when creating an account or new password for a website. It ensures that the user's password is at least 8 characters long, has at least 1 uppercase and 1 lowercase character, has at least 1 number, and at least 1 special character. It will not accept any password with periods or line breaks.

This regex can be broken down into 7 different parts:

- ``(?=^.{8,}$)`` handles the password length at 8 or more
- ``(?=.*\d)`` looks for at least 1 number
- ``(?=.*[!@#$%^&*]+)`` requires at least 1 special character
- ``(?![.\n])`` makes sure the password does not have a period or line break
- ``(?=.*[A-Z])`` is for at least 1 uppercase letter
- ``(?=.*[a-z])`` is for at least 1 lowercase letter
- ``.*$`` matches any character zero or more times until the end of the string (excluding line breaks)

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Positive and Negative Lookaheads](#positive-and-negative-lookaheads)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
The only examples of anchors in this regex are in the first set of parantheses where it requests a string of at least 8 characters and the last part where it matches strings that that end with characters that come before it. this is signified by the use of ^ and $
### Quantifiers
Quantifires are used in the 2nd, 3rd, 5th, and 6th set of parentheses as well as in the last part. The * matches characters 0 or more times and the + used only in the 3rd parentheses is looking for any of the characters in the preceeding set of brackets 1 or more times.
### Grouping Constructs
Everything but the 7th sub-expression uses grouping constructs. The parentheses, brackets, and curly braces throughout this expression separate different sub expressions to prevent any confusion when running the regex.
### Bracket Expressions
Sub-expressions 3, 4, 5, and 6 use bracket expressions to require or exclude various characters. The 4th set however uses a character class to deliver its requirements.
### Character Classes
The \n and \d character classes are used in the 2nd and 4th set of parentheses they signify a new line character and digits 0-9 respectively.
### Positive and Negative Lookaheads
The ?= is a positive lookahead that checks that the string is matching the parameters, while ?! the negative lookahead checks that the string is not matching the parameters. They can be found on almost every part of the regex.
### Character Escapes
Character escapes are a way to change the meaning of an individual character using a `\`. For example in the regex above the character classes \n and \d change the characters n and d to have new meaning by adding a \ before them.
## Author

As of now I am a Fullstack Web Development Bootcamp student hoping to pave my way through this life. Check out my github account [here](https://github.com/m-vanhoose "github account").
