# Regex Tutorial

This tutorial is intended to help developers and software development students better understand regex. Regex is short for regular expression, and can be used to find patterns of characters within strings, or find and replace character(s) within a string.

## Summary

In this tutorial, I will be explaining the regex for matching a Hex Value. This can be helpful when trying to make sure hex values for colors are being used correctly in a development project.

Regex for matching a hex value: 

```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```
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

Regex expressions are wapped in two forward slashes, for example: `/regex/`. Everything inside those two forward slashes is part of the regex and define a search pattern for matching. In the next few sections, I will define the meanings of the symbols inside of the two forward slashes of the regex for matching a hex value

```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```

In our hex value matching regex, we are looking for a string that may or may not start with `#`, followed by a 6 character or 3 character combination or letters a-f and numbers 0-9.

### Anchors

`^` and `$` are considered anchors. They can be seen after the starting / and before the ending / of our regex. The anchor `^` signifies a string that begins with some combination or an exact match of the characters that follow it. The anchor `$` signifies a string that ends with some combination or an exact match of the characters that precede it. In short, everything in between the `^` and the `$` represents what patterns the regex should be looking for. 

In our example of regex for matching a hex value, we will be matching a hex value based on the following patterns `#?([a-f0-9]{6}|[a-f0-9]{3})`

### Quantifiers

Quantifiers are used to put limits on the string or a section of the string that your regex is matching. In our example regex for matching a hex value, we use the following quantifiers:

- `?`, which matches the pattern 0 or 1 time. It is used as a binary to essentially mark the preceding pattern as optional or "lazy". In the regex for matching a hex value, the `?` follows a `#`, which means that the string we're matching can either include or exclude the #.
  
- `{}` sets limits for the amount of characters for a match. It can be used in three different ways.
  - The first way is a single number in curly brackets `{n}`. This means the pattern should have `n` characters.
  - The second way is a number and a comma in curly brackets `{n, }`. This means the pattern should have at least `n` characters but does not set a max number of characters.
  - The third way is two numbers and a comma in curly brackets `{n, x}`. This sets a min number of characters, `n`, and a max number of characters, `x`,  the match should include.
  - In the regex for matching a hex value, we see `{6}` and `{3}`. For the part of the regex preceding the `|`, 6 characters are required for the match. In the part of the regex following the `|`, 3 characters are required for the match.
    
- Other regex quantifiers that are not used in our hex value example include:
  - `*`, which matches the pattern 0 or more times
  - `+`, which matches the pattern one or more times. 
 

### OR Operator

`|` is the OR operator in regex. Using the or operator allows us to match one of multiple patterns. In the hex value example, we use `|` between the patterns `[a-f0-9]{6}` and `[a-f0-9]{3}` so that either pattern (a hex value with 6 characters OR 3 characters) can count as a match.

### Character Classes

Character classes in regex define a set of characters that can occur in a string and fulfill a match. Bracket expressions are considered character classes. More on these and how they appear in our hex code example in the Bracket Expressions section below: [Bracket Expressions](#bracket-expressions)

### Flags

Earlier I mentioned that everything in regex is wrapped in slashes `/`. Flags go after the second slash at the end of the regex, and they define additional functionality or limits of the regex. Our example of regex for matching a hex code doesn't have any flags, but I'll define the flags anyways. 

The six flags in regex are defined by (sources: https://javascript.info/regexp-introduction and https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial):

`s` - Enables “dotall” mode, that allows a dot . to match newline character \n 

`u` - Enables full Unicode support

`y` -“Sticky” mode: searching at the exact position in the text 

`g` — Global search: the regex should be tested against all possible matches in a string

`i` — Case-insensitive search: case should be ignored while attempting a match in a string

`m` — Multi-line search: a multi-line input string should be treated as multiple lines

### Grouping and Capturing

Grouping constructs are used to break strings into different sections to check whether they meet different requirements. Sections can be grouped using parentheses `()` in regex. Each section wrapped in parentheses is called a subexpression. Grouping constructs can be capturing or non-capturing. Capturing groups capture the matched sequences for reuse and non-capturing groups don't. Inserting `?:` after the first parentheses of a group makes the group non-capturing.

In our example of the regex for matching a hex value, it contains a capturing group `([a-f0-9]{6}|[a-f0-9]{3})`, which contains a bracket expression for matching. More on bracket expresssions to come in the next section.

### Bracket Expressions

We use bracket expressions `[]` to group the range of characters that we want to match. Bracket expressions outline the characters that we want to include in our requirements. Inn our example of regex for matching a hex value, `[a-f0-9]` looks for a string that contains a combination of lowercase letters a-f and numbers 0-9.

### Greedy and Lazy Match

Greedy matches match as many occurrences of the pattern as possible. Lazy matches match as few occurrences of the pattern as possible. Lazy matches will usually look for the first match that fulfills the requirement and stop there, while greedy matches will keep looking for all matches that fulfill a requirement. Matches can be made lazy by adding a ? symbol after a quantifier. 

## Author

My name is Whitney Brady. I'm a student at the University of Utah Full Stack Development Bootcamp. Here's a link to my github: https://github.com/whitbreezy
