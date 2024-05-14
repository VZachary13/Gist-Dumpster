# Regex Quick Guide

## Summary

In this guide, we will explore various components of regular expressions (regex), which are powerful tools for pattern matching and text manipulation. We'll cover essential aspects of regex, such as anchors, quantifiers, the OR operator, character classes, flags, grouping and capturing, bracket expressions, greedy and lazy matches, boundaries, back-references, and look-ahead and look-behind assertions. By understanding these elements, you'll be able to craft complex regex patterns to suit a variety of text-processing needs. Here is a regex example to match URLs: `^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$`.

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

- `^` - Matches the start of a string.
- `$` - Matches the end of a string.

Example in URL regex:

```regex
^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
```

- `^` asserts the start of the string.
- `$` asserts the end of the string.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present for a match to occur. Common quantifiers include:

- `*` - Matches 0 or more occurrences.
- `+` - Matches 1 or more occurrences.
- `?` - Matches 0 or 1 occurrence.
- `{n}` - Matches exactly n occurrences.
- `{n,}` - Matches n or more occurrences.
- `{n,m}` - Matches between n and m occurrences.

Example in URL regex:

```regex
^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
```

- `https?` matches "http" or "https" (`?` matches 0 or 1 occurrence of "s").
- `[a-z\.]{2,6}` matches 2 to 6 lowercase letters or dots.
- `([\/\w \.-]*)*` matches any number of directories and file names.

### OR Operator

The OR operator `|` allows for matching one pattern or another.

Example (simplified):

```regex
http|https
```

Matches either "http" or "https".

In the URL regex, the use of `?` is equivalent to `|` in some cases by indicating optional elements.

### Character Classes

Character classes match any one of a set of characters. They are defined using square brackets `[]`.

Example in URL regex:

```regex
^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
```

- `[\da-z\.-]` matches any digit, lowercase letter, dot, or hyphen.
- `[a-z\.]` matches any lowercase letter or dot.
- `[\/\w \.-]` matches any slash, word character, space, dot, or hyphen.

### Flags

Flags modify the behavior of the regex engine. They are placed at the end of the regex pattern, after a closing delimiter (usually `/` in many programming languages).

Example (not in the URL regex,):

```regex
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/i
```

- `i` - Case-insensitive matching.

### Grouping and Capturing

Parentheses `()` are used for grouping parts of a regex pattern and capturing the matched sub-patterns.

Example in URL regex:

```regex
^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
```

- `(https?:\/\/)?` captures the optional "http://" or "https://".
- `([\da-z\.-]+)` captures the domain name.
- `([a-z\.]{2,6})` captures the top-level domain (TLD).
- `([\/\w \.-]*)*` captures the path and optional file names.

### Bracket Expressions

Bracket expressions `[]` define a set of characters to match.

Example in URL regex:

```regex
[\da-z\.-]
```

- Matches any digit (`\d`), lowercase letter (`a-z`), dot (`.`), or hyphen (`-`).

### Greedy and Lazy Match

Quantifiers are greedy by default, meaning they match as much text as possible. Adding a `?` makes them lazy, matching as little text as possible.

Example in URL regex (note: not explicitly shown in the given regex):

```regex
.*?
```

- Greedy: `.*` matches as much text as possible.
- Lazy: `.*?` matches as little text as possible.

### Boundaries

Word boundaries are used to match positions where a word starts or ends.

Example (not in the URL regex):

```regex
\bword\b
```

- Matches "word" surrounded by word boundaries.

### Back-references

Back-references match the same text as previously matched by a capturing group.

Example (not in the URL regex):

```regex
(\d)\1
```

- Matches two consecutive identical digits.

### Look-ahead and Look-behind

Look-ahead and look-behind assertions match a group before or after a specified pattern without including it in the result.

Example (not in the URL regex):

- Positive look-ahead: `(?=pattern)`
- Negative look-ahead: `(?!pattern)`
- Positive look-behind: `(?<=pattern)`
- Negative look-behind: `(?<!pattern)`

```regex
foo(?=bar)
```

- Matches "foo" only if it is followed by "bar".

```regex
foo(?!bar)
```

- Matches "foo" only if it is not followed by "bar".

## Author

Vzachary13
