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

As regex becomes more cumbersome, you may find yourself needing to validate multiple parts of a string. This is where grouping constructs come into play. The primary way you group a section of a regex is by using parentheses (()). Each section within parentheses is known as a subexpression.

The following example contains two grouping constructs or subexpressions:

> (abc):(xyz)

The first subexpression is looking for a part of the string that matches the string "abc" exactly. Similarly, the second subexpression is looking for "xyz". In between the subexpressions, we have a colon (:). Thus, the string "abc:xyz" would match, but the string "acb:xyz" would not. Unlike bracket expressions, subexpressions look for an exact match unless they're told to do otherwise.

### Bracket Expressions

Anything inside a set of square brackets ([]) represents a range of characters that we want to match. These patterns are known as bracket expressions, but they are also known as a positive character group, because they outline the characters we want to include. We can write these expressions to include all of the characters we want to match. For example, <mark>[abc]</mark> will look for a string that includes a or b or c, regardless of the length of the string. So all of the following examples would match: "aaa", "bin" "court", "abracadabra", and "bca".

We can break down the bracket expressions as follows:

- <mark>[a-z]</mark>—The string can contain any lowercase letter between a–z. Keep in mind that this looks for lowercase characters only. If we wanted to include uppercase characters, we would need to change the expression to [a-zA-Z].

- <mark>[0-9]</mark>—The string can contain any number between 0–9

- <mark>[_-]</mark>—The string can contain an underscore or hyphen. Both the underscore and the hyphen are called special characters. Special characters include any non-alphanumeric characters, such as punctuation or symbols. In this case, we only want a string that includes \_ or -. It's important to note that the hyphen here is not the same hyphen that we used in our alphanumeric ranges. In bracket expressions, special characters that we want to include follow alphanumeric character ranges within the brackets.

If we put all of these expressions together so that our pattern is <mark>[a-z0-9_-]</mark>, this will match any string that includes any combination of lowercase letters between a and z, any number between 0 and 9, and the special characters of an underscore or a hyphen. Keep in mind that these characters can be in any order. It's also important to note that this pattern does not require the string to meet all of these requirements; it can meet any of them.

### Character Classes

A character class defines a set of characters, where one character shall match. Bracket expressions are what we consider character classes. Here are some common examples:

- .—Matches any character except the newline character (\n)

- \d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression <mark>[0-9]</mark>.

- \w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

- \s—Matches a single whitespace character, including tabs and line breaks

Note that the last three character classes can be changed to perform an inverse match by capitalizing the letter character. For example, \D matches a non-digit character.

### The OR Operator

Remember that a bracket expression does not require the string to meet all of the requirements in the pattern. This means that <mark>[a-z0-9_-]</mark> searches for alphanumeric characters or the two special characters included in the pattern. Often, you'll want to add this same logic outside of a bracket expression, especially within a grouping construct or between two different grouping constructs.

Using the OR operator (|), the expression <mark>[abc]</mark> could be written as (a|b|c). Using our example in the grouping constructs section, we can take the original expression:

> (abc):(xyz)

And then use the OR operator to convert it to the following:

> (a|b|c):(x|y|z)

Now, both of the strings "abc:xyz" and "acb:xyz" would match, as well as "a:z", but "xyz:abc" would not.

### Flags

Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression. There are six but these are three that you'll most likely come across:

- g—Global search: the regex should be tested against all possible matches in a string.

- i—Case-insensitive search: case should be ignored while attempting a match in a string

- m—Multi-line search: a multi-line input string should be treated as multiple lines

### Character Escapes

The backslash ( \ ) in a regex escapes a character. For example, we know the open curly brace ({) is the beginning of a quantifier. If the backslash is added before the curly brace ( \ { ), the regex will no be looking for the open curly brace instead of the quantifier beginning. The backslash interprets that character as a literal.

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
