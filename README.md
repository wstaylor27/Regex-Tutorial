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

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
