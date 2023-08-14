# Explaining a Hex Code Regex

## Description

In this gist I will be describing the different parts of a hex regex; I will also be segmenting this regex code into small digestible parts and explaining each of their individual functions within the code. I am going to be tackling the Hex regex code, as I said earlier and I will be breaking down the parts of it section by section  as well as explaining the dilleniation between the sections and why I know each section is a section in and of itself. I will also be providing examples of what would/wouldn't work within each of the regex section's parameters.

## Summary

The regex I will be describing is the Hex Code Regex. This is basically a code string that determines what passes as a Hex Code. It sets parameters and essentiallhy says, "If code is trying to pass as a hex code, it has to be like this or else it will not be a hex code and if we use the regex to search for a hexcode outside of those parameters, it wont be found." I will be talking about this section: '/^#?', this section: '[a-f0-9]{6}', this: '|', '[a-f0-9]{3}', as well as '$/'. I will be breaking down their individual parts and how they operate as well as how and why they are placed in this order.
The full regex code is as follows: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Boundaries](#boundaries)

## Regex Components

### Anchors
The "/^" acts as sort of the boundary before the bondary. The boundary bfore the anchor in more adequate terms. The "/^" is essentially placing the boundary of the regex with the "/" and the "^" is declaring the start of the line. The beginning of this regex code also says that the "#" symbol is optional by making the statement "#?". The regex statement is also terminated at the end by putting "$/" The "$" means "this is the end of the statement" and the "/" is indicating the end of the line.
An unacceptable parameter in this area would be: Any character outside of the acceptable parameters such as "\" or any number or letter.
So far we have covered: `/^#?_________________________$/`
### Quantifiers
The quantifiers are as follows "{6}" and/or "{3}" we will go into why they are placed where they are placed in more detail a little later, but whenever a number is placed within curly braces, they are essentially setting a number limit/requirement for whatever parameters are proceeding the curly braces. In this case, the characters that are acceptable in a hex code is what proceeds the quanitifiers. 
An acceptable parameter in this area would be:{1,3} <-- this would work in curly braces in other regex codes NOT for hexcodes. A number is needed and nothing else
An unacceptable parameter in this area would be: {a} or {/}
We have now covered: `/^#?_________{6}_________{3}_$/`
### OR Operator
There is an OR operator in the regex code. "|" is found between the first qaunitifer and the next bracketed section. This is basically saying that the parameters in the bracketed section before or the backeted section after the pipe are acceptable in order to form a hexcode. We have now covered the "|" in the regex code. 
An acceptable parameter in this area would be: _______ "|" _______. If you are going to have a pipe, there is something needed before and after the pipe that indicates "or".
An unacceptable parameter in this area would be: ________ or ________.
In total, we have covered: `/^#?_________{6}|________{3}_$/`
### Character Classes
Character classes are the characters within a bracketed section. This dictates what will be taken as an acceptable character within the regex code. In the Hexcode regex they are as follows "[a-f0-9]" in the first bracketed section and "[a-f0-9]" as well in the second bracketed section. This is important because it limits which characters are acceptable within the Hexcode.
An unacceptable parameter in this area would be: [abcdefghijklmnop,0123456789] this would not work because of the syntax as well as some of the letters are outside of hexcode parameters.
We have now covered: `/^#?_[a-f0-9]{6}|[a-f0-9]{3}_$/`
### Grouping
There is a use of grouping in this regex code, it is a large grouping but a grouping nonetheless. We see it right after the anchors and boundaries. "()" is found right before the brackets and after the final quantifier. It is essentially saying that all that is within the "()" is going to be grouped together as one string of code.
An unacceptable parameter in this area would be:  "()" passing a group with nothing inside of it.
We have now covered: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` thus finishing the regex expression.
### Bracket Expressions
As indicated within the character classes section, there are brackets within this regex. "[]" hold the character parameters for the hexcode within the regex. Without these, the numbers and letters would have a whole new meaning.
An unacceptable parameter in this area would be:
### Boundaries
As covered in the Anchors section there are boundaries at the beginning and the end of the regex code. "/" and "/" are at the very beginning and end of the code indicating the beginning and end of the regex, obviously. This is important because it lays out a clear beginning and end point for the regex code.
## Author

My name is Noah Nelson, I am a learning full stack developer who is aspiring to make it into the amazing world of computer developement. For more of my projects, check out the link below:
https://github.com/noahSPICE

