Uncoding the Mystery of Regex 

Regex sounds like a Futuristic Techno Club but its actually much cooler than that. Regex appears to be a set of randomized characters but it better serves as a coded langaue the computer and developers use to define a search pattern, within a body of text. It uses a combination of "Literal" and "Meta" characters to locate specific or sensitive information.

## Summary

I will be covering the retrieval of Emails with Regex. Often Emails fall under sensitive information so its important, as a Developer to be able to distingush Regex sequence structure to keep information private. Below is an example of a Regex sequence for identifying an email.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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
Anchors are responsible for matching the postion of a sting. Allowing a search to know where to start and end in the pattern.

`^`: This is the anchor that specifies the start of the string.
`$`: This is the anchor that specifies the end of the string.

### Quantifiers
Quantifiers tell a serach how many times to expect a charater, group or character class. If a pattern occurs a specific number of times or within a certain range.

`+`: Appears after the character classes inside the capturing groups. It matches "one or more" of the preceding elements.

`{2,6}`: In the third capturing group, it specifies that the preceding element must appear between 2 and 6 times.

### OR Operator
`|`: The OR operator is used to match one of several possible patterns. Take an example of `apple|orange`, this will find either the word "apple" or the word "orange" in a text.

The OR operator isn't used here.

### Character Classes
Using the `[]` you can match a specific character(s) in a group of characters.

`\d`: This is a shorthand character class that matches any digit (0-9).
`[a-z0-9_\.-]`: This character class matches any lowercase letter, digit, underscore `(_)`, period `(.)`, or hyphen `(-)`

### Flags
Flags or modifiers change the way a pattern is matched. They control things like case sensitivity, multi-line behavior, and more. You usually apply flags at the end of the Regex pattern, or in some languages, they can be set within the Regex function.

This Regex does not use any Flags. Flags like `i` (case-insensitive) or `g` (global search) would typically appear after the closing `/`

### Grouping and Capturing
By using the `()` we can treat multiple characters as a Group / single unit. Capturing saves or remembers matched content in a Regex engine.

`([a-z0-9_\.-]+)`: Captures the part of the email before the @.
`([\da-z\.-]+)`: Captures the domain name part of the email (after the @).
`([a-z\.]{2,6})`: Captures the top-level domain (like .com or .org).

### Bracket Expressions
Very similar to Character classes uses the `[]` to specify a set of characters you want to match.

`[a-z0-9_\.-]`: This bracket expression matches any character within the specified range (letters, digits, underscore, period, hyphen).
`[\da-z\.-]`: This bracket expression matches digits, lowercase letters, periods, and hyphens.
`[a-z\.]`: This matches any lowercase letter or period.

### Greedy and Lazy Match
Greedy and Lazy (or non-greedy) matching refer to these quantifiers `(*, +, ?, {min,max})` and how they help matching patterns.

A greedy match tries to match as much of the input as possible. By default, regex quantifiers are greedy.

A lazy match tries to match as little of the input as possible. Adding a `?` for exaample will match the fewest characters as possible in a serch.

### Boundaries
The anchors `^` and `$` act as boundaries, ensuring that the pattern must match the entire string from start to end. Our Regex matches the entire email so we dont need `Word boundaries (\b)` to seperate words.

### Back-references
We can request the Regex Engine to remember captured content by enclosing part of the pattern in `()`. This then groups the content in "capturing groups" refrenced by `\1, \2,` etc. There are no Back-references in this Regex

### Look-ahead and Look-behind
A Look-ahead and Look-behind serves as a true or false condition by matching patterns based on what comes before or after a certain position in a given sting.

A look-ahead can be Positive or Negative meaning, A Positive Look-ahead `(?=pattern)` checks if the pattern is present after the current position. While a Look-behind `(?!pattern)` checks if the pattern is not present after the current position. 

A Look-behind has two forms too. A Positive Look-behind `(?<=pattern)` and a Negative `(?<!pattern)`. A Positive checks that the pattern is present before the current position. A Negative checks that the pattern is not before the cureent position.

## Author
I am a Student Developer with a future in writing my or Regex. You'll see my Github below. Thank You!

Github: https://github.com/sickcurse/Mystery_Regex