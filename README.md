# Regex-Tutorial

Introductory paragraph (replace this with your text)

## Summary

In this repo, I will be describing the various components of **regular expressions** or **"regex"**. So what is regex? Regex is a series of patterns used to match character combinations in strings. Before we get started, let's breakdown a basic regex

> /^[a-z0-9_-]{3,16}$/

The regex above validates a specific criteria. This is how it is broken down:

- The string can contain any lowercase characters between a-z
- The string can contain any numbers between 0-9
- The string can contain any underscore or hyphen
- The string is 3-16 characters in length

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

Prior to diving into each component, let's cover the basics of a regex. A regex is a literal, therefore, the pattern we define must use literal notation's parameters i.e. wrapped in slashes (/).

### Anchors

There are two anchor characters in regex: <mark>^</mark> and <mark>$</mark>.

The <mark>^</mark> identifies a string that begins with the characters that come after it, while <mark>$</mark> identifies a string that ends with the characters that come before it. For example, <mark>^to</mark> would match strings like <mark>"to</mark> or <mark>"to go"</mark> but not <mark>"To go"</mark>. This is because regex is case-sensitive.

AS stated earlier, <mark>$</mark> signifies a string that ends with the characters that come before it. It can be preceded by an exact string or a range.

In our first regex, <mark>[a-z0-9_-]{3-16}</mark>, we notice {3-16} comes before <mark>$</mark>. This is called a quantifier. It validates the string's minimum and maximum character length.

### Quantifiers

Quantifiers state the numbers of characters or expressions to match. They typically include minimum and maximum values for your regex. Here are some common patterns:

- \*—Matches the pattern zero or more times

- +—Matches the pattern one or more times

- ?—Matches the pattern zero or one time

- {}—Curly brackets can provide three different ways to set limits for a match:

  - { n }—Matches the pattern exactly n number of times

  - { n, }—Matches the pattern at least n number of times

  - { n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times

### Grouping Constructs

### Bracket Expressions

### Character Classes

A character class defines a set of characters, where one character shall match. Bracket expressions are what we consider character classes. Here are some common examples:

- .—Matches any character except the newline character (\n)

- \d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

- \w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

- \s—Matches a single whitespace character, including tabs and line breaks

Note that the last three character classes can be changed to perform an inverse match by capitalizing the letter character. For example, \D matches a non-digit character.

### The OR Operator

### Flags

Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression. There are six but these are three that you'll most likely come across:

- g—Global search: the regex should be tested against all possible matches in a string.

- i—Case-insensitive search: case should be ignored while attempting a match in a string

- m—Multi-line search: a multi-line input string should be treated as multiple lines

### Character Escapes

The backslash ( \ ) in a regex escapes a character. For example, we know the open curly brace ({) is the beginning of a quantifier. If the backslash is added before the curly brace ( \ { ), the regex will no be looking for the open curly brace instead of the quantifier beginning. The backslash interprets that character as a literal.

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
