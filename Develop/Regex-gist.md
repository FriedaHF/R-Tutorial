# R-Tutorial

Regex, which stands for regular expression, is like a superhero tool for finding patterns and playing with text. So, in this big guide, we're gonna dig into all kinds of things about regex, taking apart its pieces and explaining what they do. We want to make regex less confusing by talking about it in a simple way and showing how it works with real examples.

## Summary

We're going to look at a special regex pattern made to find email addresses. It's like a tool that helps us understand how regex works by seeing it in action. Here's what the regex pattern looks like:

 ```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

- The `^` symbol in the email pattern marks the beginning of the string. For instance, `^The` would search for strings starting with "The."
- The `$` symbol denotes the end, so the email should conclude with the `([a-z\.]{2,6})` expression. For instance, `end$` searches for strings ending with "end."

### Quantifiers

- `*` means one or more occurrences. For example, `cde*` matches "cd" followed by zero or more "e."
- `+` indicates one or more occurrences, similar to `*`.
- `?` represents zero or one occurrence, making `cde?` match both "cd" and "cde."
- `{}` sets a custom range. If `cde{2}`, it matches "cdee."

### OR Operator

- The `|` symbol acts as a logical OR. For example, `abc|xyz` matches either "abc" or "xyz."
- `[]` works similarly to `|` by selecting characters within brackets.

### Character Classes

- `\d` matches a single digit.
- `\w` matches a word character, which can be a letter or a digit.
- `\s` matches a white space.
- `.` matches any character.

### Flags

- The `/` symbol creates a regex between the slashes. In the email regex, it is seen at the start and end.
- `/g` enables global search, returning after the first search.

### Grouping and Capturing

- `()` creates a capturing group. For example, in `c(ba)`, only "cba" is a match.
- `?:` disables capturing groups. In `a(?:bc)`, both "abc" and "a" match.

### Bracket Expressions

- `[]` matches anything within brackets. For instance, `[abc]` matches "a," "b," or "c."
- `[a-c]` is equivalent to the above expression.
- `[a-fA-F0-9]` matches any letter from "a" to "f," "A" to "F," and "0" to "9."
- `[^a-zA-Z]` matches any letter except "a" to "z" and "A" to "Z."

### Greedy and Lazy Match

- **Greedy Search:**
  - Greedy operators `( * + {})` expand the match as far as possible. They try to match the longest string.

- **Lazy Search:**
  - `?` in `/".+?"/g` lazily matches characters between double quotes. For example, in `"Coding" is fun.`, only "Coding" is searched.

### Boundaries

- `\b` searches for a whole word. For example, `\bapple\b` matches only "apple," not "greenapple" or "redapple."

### Back-references

- `([abc])\1` matches consecutive characters like "aa," "aaaaaa," "bb," "bbbbbb," and "cc," "cccccc."

### Look-ahead and Look-behind

- `d(?=g)` matches only "d" followed by "g," for example, "dg" but not "dt."
- `(?<=f)g` matches only "g" preceded by "f," for example, "g" in "gf," excluding "f" from the match.

## Author

[GitHub](https://github.com/FriedaHF/R-Tutorial)
