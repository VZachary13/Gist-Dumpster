# Regex Quick Guide

## Summary

In this guide, we will explore various components of regular expressions (regex), which are powerful tools for pattern matching and text manipulation. We'll cover essential aspects of regex, such as anchors, quantifiers, the OR operator, character classes, flags, grouping and capturing, bracket expressions, greedy and lazy matches, boundaries, back-references, and look-ahead and look-behind assertions. By understanding these elements, you'll be able to craft complex regex patterns to suit a variety of text-processing needs. Here is a basic regex example: ^(\d{3})-(\d{2})-(\d{4})$.

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

Anchors are special characters in regex that match positions within a string, rather than actual characters. The two main anchors are:

^ - Matches the start of a string.
$ - Matches the end of a string.
Example: ^Hello matches "Hello" at the beginning of a string, and world$ matches "world" at the end of a string.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present for a match to occur. Common quantifiers include:

- - Matches 0 or more occurrences.

* - Matches 1 or more occurrences.
    ? - Matches 0 or 1 occurrence.
    {n} - Matches exactly n occurrences.
    {n,} - Matches n or more occurrences.
    {n,m} - Matches between n and m occurrences.
    Example: a{2,4} matches "aa", "aaa", or "aaaa".

### OR Operator

The OR operator | allows for matching one pattern or another.

Example: cat|dog matches either "cat" or "dog".

### Character Classes

Character classes match any one of a set of characters. They are defined using square brackets [].

[abc] - Matches any one of the characters a, b, or c.
[^abc] - Matches any character except a, b, or c.
[a-z] - Matches any lowercase letter.
[0-9] - Matches any digit.
Example: [A-Za-z] matches any uppercase or lowercase letter.

### Flags

Flags modify the behavior of the regex engine. They are placed at the end of the regex pattern, after a closing delimiter (usually / in many programming languages).

i - Case-insensitive matching.
g - Global matching (find all matches).
m - Multi-line matching.
Example: /hello/i matches "hello", "Hello", or "HELLO".

### Grouping and Capturing

Parentheses () are used for grouping parts of a regex pattern and capturing the matched sub-patterns.

Example: (abc)+ matches one or more repetitions of "abc".

### Bracket Expressions

Bracket expressions [] define a set of characters to match.

Example: [0-9] matches any single digit.

### Greedy and Lazy Match

Quantifiers are greedy by default, meaning they match as much text as possible. Adding a ? makes them lazy, matching as little text as possible.

Greedy: a._b matches the longest string starting with "a" and ending with "b".
Lazy: a._?b matches the shortest string starting with "a" and ending with "b".

### Boundaries

Word boundaries are used to match positions where a word starts or ends.

\b - Matches a word boundary.
\B - Matches a non-word boundary.
Example: \bword\b matches "word" surrounded by word boundaries.

### Back-references

Back-references match the same text as previously matched by a capturing group.

Example: (\\d)\\1 matches two consecutive identical digits.

### Look-ahead and Look-behind

Look-ahead and look-behind assertions match a group before or after a specified pattern without including it in the result.

Positive look-ahead: (?=pattern)
Negative look-ahead: (?!pattern)
Positive look-behind: (?<=pattern)
Negative look-behind: (?<!pattern)
Example: foo(?=bar) matches "foo" only if it is followed by "bar".

## Author

Vzachary13
