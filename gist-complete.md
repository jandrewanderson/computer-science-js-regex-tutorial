# Computer Science JS Regex Tutorial



The purpose of this assignment is to explain how to use a specific regular expression or regex. This tutorial will show a step by step explanation of what the regular expression is doing and what each symbol means.



## Summary

The regular expression that I am going to be explaining today is this:

```/^[0-9]{5}(?:-[0-9]{4})?$/```

This is the regular expression used for finding United States zip codes. 



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Resources](#resources)



## Regex Components



### Anchors

The characters `^` and `$` are the anchors that are being used in this regular expression.

The `^` symbol is what begins a string. Everything that follows this are the parameters that are being searched with this regular expression

The `&` symbol is what ends the string started by the `^` symbol. 

Both of these symbols are used to begin and end the string of possible matches. These matches can be an exact string or the can be a range of possible matches. In our case we are looking for a range of different characters, the specifics of which will be explained in the following sections.



### Bracket Expressions

In the regular expression we are using, we are utilizing something called bracket expressions. Anything that is being included between square brackets, `[]`, is what we are trying to find a match of in our search. Hypens, `-`, are often used to help us refine our search. In our example we see `[0-9]`, which simply means that we are looking for any characters between 0 and 9. 



### Quantifiers

This regular expression contains multiple qunatifiers.

The obvious ones are `{5}` and `{4}`.

Quantifiers are what sets the limits of the string, which is usually set to the length of the string. For example, in our case, the `{5}` is showing that we are looking for anything that matches what we put before this with a length of 5 characters.

There is one more quantifier in our expression that is not as easy to spot. It is the `?` found towards the end. All this is doing is saying that everything in our expression has to match between 0 and 1 times.


### Grouping Constructs

The expression being used also contains a grouping construct. These are displayed by using `()` in our expression. Our expression does use a set of parenthesis in the second half displayed like this:

```(?:-[0-9]{4})```

Grouping is what allows us to get subexpressions. If the overall expression is in group 0, that would put anything in this set of parenthesis into group 1. This allows us to search for seperate pieces of data that may or may not be included in the overall string.

In our case this is what is called a non-caputuring group. Here is a brief definition taken from one of my resources below: 

    "Non-capturing groups match exactly the way normal groups do. However, they do not make their matched content available. If there’s no need to capture the content, they can be used to improve matching performance. Non-capturing groups are written as: (?:pattern)" 

This group is for the last four digits that are included in the zip code that also starts with a `-`. The last four digits are used to greater specification on a location, however, they are not included more often than not when it comes to documentation of addresses. In our case it made more sense to search for the last four digits, but not include them, as they don't possess the same relevance as the first five digits.



### Character Classes

In our example we do not contain one of these, but here is a definition taken from one of our resources below:

    "A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. We've actually already discussed some character classes. The bracket expressions outlined previously, including positive and negative character groups, are considered character classes."



### The OR Operator

In our example we do not contain one of these, but here is a definition taken from one of our resources below:

    "Remember that a bracket expression does not require the string to meet all of the requirements in the pattern. This means that [a-z0-9_-] searches for alphanumeric characters or the two special characters included in the pattern. Often, you'll want to add this same logic outside of a bracket expression, especially within a grouping construct or between two different grouping constructs.

    Using the OR operator (|), the expression [abc] could be written as (a|b|c). Using our example in the grouping constructs section, we can take the original expression:

        (abc):(xyz)

    And then use the OR operator to convert it to the following:

        (a|b|c):(x|y|z)

    Now, both of the strings "abc:xyz" and "acb:xyz" would match, as well as "a:z", but "xyz:abc" would not."

### Flags

In our example we do not contain one of these, but here is a definition taken from one of our resources below:

    "We started this tutorial by explaining that as a literal, a regex must be wrapped in slash characters. The one exception to this rule is with the component known as flags. Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex. There are six optional flags that can be used, either separately or together and in any order, but these are the three you're most likely to encounter:

        - g—Global search: the regex should be tested against all possible matches in a string.

        - i—Case-insensitive search: case should be ignored while attempting a match in a string

        - m—Multi-line search: a multi-line input string should be treated as multiple lines"
        



### Character Escapes

In our example we do not contain one of these, but here is a definition taken from one of our resources below:

    "The backslash (\) in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a backslash before the open curly brace (\{) means that the regex should look for the open curly brace character instead of beginning to define a quantifier. This is common when looking for strings with special characters that are the same as a particular component of a regex.

    It's important to note that all special characters, including the backslash (\), lose their special significance inside bracket expressions."



## Author

Joseph Andrew Anderson

[Link to my Github repo](https://github.com/jandrewanderson/computer-science-js-regex-tutorial)



## Resources

https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial

http://geniuscarrier.com/common-regular-expressions-in-javascript/

https://towardsdatascience.com/everything-you-need-to-know-about-regular-expressions-8f622fe10b03