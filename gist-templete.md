# Regex Tutorial: Matching an Email

Regular expressions, or regex, are like powerful search tools for finding patterns in text. In this tutorial we will be explaining how that is incorporated in an email expression using regex. 

## Summary

 ```md
 We will be breaking down the use of regex to match emails using this expression:
  
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

  ```

 By creating a regex pattern to match email addresses, we can easily validate and extract email data from text. This helps a lot with tasks like checking if an email address is correctly formatted or extracting email addresses from a larger piece of text.

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

| Symbol   | Description |
| -------- | ----------  |
|  ^ | This caret symbol represents the start of a string. It ensures that the pattern must start at the beginning of the string.|
|  $ | This dollar sign symbol represents the end of the string. It ensures that the pattern must end at the end of the string.|

* These anchors ensure that the entire string must match the pattern from start to finish, in this case, ensuring that the email address is the entire content of the string being evaluated.


### Quantifiers


### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author
 Shandy Cerda,

I am a dedicated web development student who is passionate about learning and eager to see where this journey takes me.For further insights into my work, feel free to explore my [Github profile](https://github.com/scerda8).