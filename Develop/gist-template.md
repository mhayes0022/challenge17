# Title (replace with your title)

The purpose of this tutorial is to give a brief introduction to regular expressions, or regex, by explaining a single regex function in depth. Each section of the tutorial outlines a different element of the regex function, and the table of contents provides links that, when clicked, will bring you directly to the desired section. 

## Summary

The regular expression, or regex, that will be explained in this tutorial is used to validate an email. While it doesn't validate whether the email exists or is available, it does check that the format of the email submitted is valid, and follows the pattern email@test.com. 
This function is seen below:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

A regex function must be surrounded with slashes '/', as denoted in the example above. We will break down the regex function by components, beginning with anchors.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Author](#author)

## Regex Components

### Anchors
Anchors signify a string that begin with the characters that follow or precede it. In the example regex, the anchors '^' and '$' are used. The anchor '^' is used to signify to begin with the characters that follow. For example, '^be' denotes any string that begins with the characters 'be', such as 'before'. Conversely, the anchor '$' signifies any characters that come before it. An example of this would be 'ter$', where the anchor is denoting the characters 'ter', and would return any strings that end with the characters 'ter', such as the word 'after'.
 
In the example regex that validates emails, the anchor '^' is used at the beginning, and the anchor '$' at the very end. 

### Quantifiers
Quantifiers set limits to the string being validated by the regex function. Commonly, and in the example, the quantifier {} is used to set limits on the number of characters used within the string being validated.

The example contains the following segmet: '{2,6}'. The numbers within denote the minimum and maximum number of characters allowed. So, in this case, the final segment of the regex requires at least two characters, and no more than six. 

### Grouping and Capturing
Regex expressions are divided into 'groups' using parentheses '()'. Each set of characters within a set of parantheses () is called a subexpression. When characters appear outside of parantheses, they become literals, meaning the regex expression will be looking for that exact character in that exact placement of the user input. 

The above example is split into three groups using parentheses. So,
([a-z0-9_\.-]+), 
([\da-z\.-]+), and 
([a-z\.]{2,6}). 

It also has several characters outside of the parantheses;
the '@' symbol, and '\.'. So, the user input must contain the '@' symbol inbetween the expected characters inside the first and second group, and have a period inbetween the second and third group. 

### Bracket Expressions
Characters placed inside of bracket expressions '[]' denote a range of characters that the input must match. These can also be called a 'positive character' group, because they define the characters that can be included. 

In the example, there are three sets of bracket expressions; the first is 
'[a-z0-9_\.-]'
The hyphen is used to denote a range of characters that can be used. So, in the above example, the first section, 'a-z', means that this section of the user input can include any lower case letter(s) from a to z. The following characters in the example, '0-9', means that it can also include any numeric characters between 0-9. The last set of characters within our example are '_-\-', which are being used as special characters. This means that in addition to allowing for any lowercase letter and any numeric character, this section of the Regex also allows for the use of those special characters.
We also have the following bracket expressions in the example regex function:
[\da-z\.-] and [a-z\.].
In the section [\da-z\.-], the '\d' will be discussed below, in the character classes section of this tutorial. The following characters, 'a-z\.-', denote that the user input in that segment can include any letters from a-z, and any of the literal characters '\', '.', or '-'.
The last segment of bracket expressions in the example denotes that we can use any lowercase letter from a-z, and the backslash and period characters.

### Character Classes
There are multiple character classes used within regex; a character class defines a set of characters. Only one is needed to meet the requirements the regex function is validating, although more than one can appear. Common character classes include: '.', '\d', and '\w'. The period, '.', matches any character except the newline character (\n). A backslash followed by the letter 'd' matches any numeric digit (this special class denotes the same thing as [0-9], explained in the section above). The backslash followed by the letter 'w' matches any alphanumeric character from the Latin alphabet, making it equivalent to [A-Za-z0-9]. 

The example function uses the '\d' special class:
([\da-z\.-]+)
In context, this means that the above statement allows for any uppercase AND any lowercase letters between a-z, and any numeric characters between 0-9.

### Greedy and Lazy Match
In addition to the quantifiers listed in the corresponding section above, there are also several other quantifiers used in the example. All quantifiers are 'greedy', meaning they match as many instances of the pattern they are denoting as possible.

Alongside the quantifier '{}' being used in the example, the quantifier '+' is used as well. This quantifier means that the pattern preceding it can be matched one or more times.

## Author

The author of this regex tutorial is currently a student taking a fullstack coding bootcamp through the University of Minnesota. Below is a link to the author's git hub account.

https://github.com/mhayes0022
