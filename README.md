# Regex Matching URL

A regular expression or regex is a sequence of characters that specifies a search pattern in text to validate the user input. This tutorial will help with breaking down a regex for matching a URL. The following gist gives a thorough description of the central components in matching a given URL utilizing regular expressions in Javascript.

## Summary

The following regex can be used to validate a URL and has been broken down in this tutorial by its components. Each section will describe the symbol, a description, and where the code is found within the regex. In the regex this URL matches any valid URL.

/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

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

While this expression may seem complicated from first glace, let's see if we can't break it down into its individual elements in order to understand how the sequence works and gain a better overall understanding of this expression.


### Anchors

The two principal anchors in this regex expression are the ^ at the beginning and the $ at the end which constitute an exact string match with the components included within the two anchors. When used alone, the ^ anchor matches any string that begins with the characters that follow the anchor. The $ matches any string that ends with the characters that precede it. By enclosing the regex between these two anchors, we are asking the search function to match exactly is included between them (what it begins AND ends with).

### Quantifiers

Quantifiers are used to specify how many times a character or group of characters should be matched. In this expression, the question mark (?) is used as a quantifier to match either 0 or 1 instances of the preceding character or group. The asterisk (*) is also used as a quantifier to match 0 or more instances of the preceding character or group.


### OR Operator

The main OR operator used in the above regex is the []. The expression will match for any characters or character classes included in the brackets. For example the [\da-z\.-] expression matches for any digits (\d) OR any characters between a and z (a-z) OR any '.' (\.) OR any '-' (-).

### Character Classes

Character classes are used to match any one character from a set of characters. In this expression, character classes are used to match specific characters within the URL. For example, [\da-z] is used to match any lowercase letter or digit, and [a-z.] is used to match any lowercase letter or period.


### Flags

Flags are used to modify the behavior of the regular expression. In this expression, no flags are used.

### Grouping and Capturing

Grouping and capturing is used to group characters together and capture the matched text for later reference. In this expression, grouping is used to group characters together, as seen with the parentheses around certain parts of the expression. Capturing is not used in this expression.

### Bracket Expressions

Bracket expressions are used to match a range of characters. In this expression, bracket expressions are used to match a range of characters within the URL. For example, [/\w .-] is used to match a forward slash, word character, space, period, or hyphen.

### Greedy and Lazy Match

Greedy and lazy match refer to how the regular expression engine handles repetition. A greedy match will try to match as many characters as possible, while a lazy match will try to match as few characters as possible. In this expression, greedy match is used, as seen with the use of the asterisk (*) quantifier.

### Boundaries

Boundaries are used to specify where a match can occur within a string. In this expression, no boundaries are used.

### Back-references

Back-references are used to refer back to a previously matched group. In this expression, back-references are not used.

### Look-ahead and Look-behind

Look-ahead and look-behind are used to match a pattern before or after the current position in the string. In this expression, look-ahead and look-behind are not used.

## Author

This regex tutorial was created by Ryan Park. Github: ryanparketh