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

Notice that some of the components of capture groups end with a ? or a *. These are generally known as quantifiers. Quantifiers are used to define the number of times a given expression may be identified. The ? makes a single instance of the character preceding the quantifier optional, whereas the * makes multiple instances of the characters preceding the quantifier optional. For example, the grouping

(https?:\/\/)?
contains two ? quantifiers. This expression is looking for an http:// OR an https://. For this reason a single internal s is optional. The same is true for the entire expression included in the parenthesis, for which reason it is followed by a ?. In other words, a valid URL may begin with http:// OR https://, or it may not begin with either of them at all (the input begins with www.). The same applies for the / at the very end of the expression.

Similarly, the * makes the expression optional, but in this case it may be one or more instances that are optional. So if we look at the fourth grouping:

([\/\w \.-]*)*
The expression is allowing for any number of filepath characters that may follow an initial specified domain.

Finally, the {} quantifier defines a range of possible instances where a match may be identified. In evaluating the Top level domain, the regular expression allows for the top level domain to consist of 2 to 6 characters.


### OR Operator

The main OR operator used in the above regex is the []. The expression will match for any characters or character classes included in the brackets. For example the [\da-z\.-] expression matches for any digits (\d) OR any characters between a and z (a-z) OR any '.' (\.) OR any '-' (-).

### Character Classes

The main character classes to consider in the above expression include the \d character class which looks for any digit, and the \w character class that looks for any alphanumeric character.


### Flags
Flags are used to set options for the regex. Some common flags include:

i: Ignore case
g: Global search (find all matches rather than stopping after the first match)
m: Multiline search (allow the caret (^) and dollar sign ($) to match the start and end of lines in addition to the start and end of the string)

### Grouping and Capturing

So what is included between the two anchors. If we examine the expression, we can see that there are a number of components separated by parentheses (). Parentheses are used in regex to create separate groups of interest. Within each of these groups, there is a regex that we may look at separately to see what is evaluated. These include:

the initial https component: (https?:\/\/)
the domain name (e.g. www.google, or pets): ([\da-z\.-]+)\.
the top level domain (.com, .gov, etc): ([a-z\.]{2,6})
the file path: ([\/\w \.-]*)*

### Bracket Expressions

Bracket expressions are similar to character classes, but they allow you to specify a range of characters to match. For example, the bracket expression [a-z] will match any lowercase letter.

### Greedy and Lazy Match

By default, regexes are greedy, which means that they will try to match as much as possible. Lazy match, on the other hand, will try to match as little as possible. You can make a regex lazy by adding a ? after the quantifier.

### Boundaries

Boundaries are used to specify where a match can occur within a string. In this expression, no boundaries are used.

### Back-references

Back-references are used to refer back to a previously matched group. In this expression, back-references are not used.

### Look-ahead and Look-behind

Look-ahead and look-behind are used to match a pattern before or after the current position in the string. In this expression, look-ahead and look-behind are not used.

## Author

This regex tutorial was created by Ryan Park. Github: ryanparketh