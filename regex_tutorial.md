# Regex Tutorial

This will go over the basic details about regular expressions. I will be going over a basic email regex. 

## Summary

The Regex below is a simple regular expression to match email addresses. 
Note the /'s at the start and ending of the expression. All regular expressions are wrapped in /'s.
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
It's looking for a basic email address with a-z, 0-9, _, ., and -'s all accepted. Wondering what that random \ is before the .? You'll find the answers to your question and any more you have in this document! (Hint: "Character Escapes"). It is also looking out for an @ symbol and so much more after it! I hope my description of regular expressions help!

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Author](#author)

## Regex Components

### Anchors

The `^` and `$` are both anchors when it comes to regex's. The `^` signifies the start of a string, where the `$` signifies the end. In a simple basic expression using only anchors like this: ^carol$ ... would only find words matching "carol" and it would be case sensitive. So this would successfully find any word exactly matching "carol", but "Carol" would be excluded.

### Quantifiers

There are 4 different quantifers when dealing with regular expressions. 

 *  matches your given pattern zero or more times.
 +  matches your given pattern one or more times.
 ?  matches your given pattern zero or ONE time.
 {} and these...Curly brackets are special. They allow 3 different ways to limit your match.

 { 2 } will match your given pattern exactly 2 times.
 { 6 } will match your given pattern AT LEAST 6 times.
 { 2, 6 } will match your given pattern AT LEAST 2 times up to a MAXIMUM of 6 times. 

 Quantifiers can be LAZY if you want then to, meaning they will match as few times as possible. Just add a $ symbol after it. 


### Grouping Constructs

Grouping constructs take in subexpressions and look for parts of strings that match the criterea exactly. With this example: (hun) will search for the exact string or phrase "hun". "hnu", "uhn", etc will NOT be an exact match so it will not be found.

### Bracket Expressions

A bracket expression is brackets [] with rules set inside. The bracket expression [a-z0-9], for example, will look for or accept every letter in the alphabet and numbers 0-9. Of course emails can and usually ARE a lot more complicated than this, this gives you an idea what a bracket expression is and how it would be used.

### Character Classes

Some common character classes used in regular expressions are: ".", "\d", "\w", and "/s". 

+ . will match any character EXCEPT "/n" (a line break).
+ \d will match ANY number. It's just shorthand for [0-9] in your expression.
+ \w will match ANY letter OR number INCLUDING underscore "_". It is just a shorthand or equivalent to [a-zA-Z0-9__]. (A-Z upper or lower case, 0-9, and underscore).
+ \s will match any single whitespace character. This includes tabs and line breaks. 

Interestingly enough, each of these, except ".", can be inversed to match it's opposite by just capitolizing the letter. 

### The OR Operator

If we take our (hun) example earlier and use the OR operator | we can widen our matches a little bit. With this example: (h|u|n) it will find any variation of h, u and n and find it as a match. "hun", "hnu", "nuh", etc...

### Flags

Unlike everything else in a regular expression flags are placed outside. They are placed after the closing "/" and they are used to define more functionality or more limitations. There are 3 flags used in regular expressions:

+ g  The global search. This will tell your regular expression to test itself aginst all possible matches in a string.
+ i  The case-INsensitive search. Basically, you don't care about case sensitivity. 
+ m  The multi-line search. Treat the input string as multiple lines. 

### Character Escapes

If we want to use regular expression characters in our regex we have to use a backslash \. The backslash lets us include a character that would otherwise be taken literally. the curly bracket { for example. If we want to include that in our regular expression we need to use \{ to tell our expression that it is NOT in fact starting a quantifier. 

## Author

[Hunter McGrew](https://github.com/HunterMcGrew)

For class

