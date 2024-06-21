# Regex Tutorial: Matching an Email

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
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

### Anchors

| Symbol   | Description |
| -------- | ----------  |
|  ^ | This caret symbol represents the start of a string. It ensures that the pattern must start at the beginning of the string.|
|  $ | This dollar sign symbol represents the end of the string. It ensures that the pattern must end at the end of the string.|

* These anchors ensure that the entire string must match the pattern from start to finish, in this case, ensuring that the email address is the entire content of the string being evaluated.


### Quantifiers
` Quantifiers determine how many times a character or a group of characters can appear.`

1. `+` which is shown in 1 or more occurrences.
  * Used in `[a-z0-9_\.-]+` which indicates the "username" in the beginning of the email
  * Then it's used in `)@([\da-z\.-]+` which indicates the "email service provider" after the user's email name in the email
  * Lastly it's used in `)\.([a-z\.]` which indicates the "domain extension" (examples:`.com , .org, .edu, .net`) after the `@` in the email
    
2. `{2,6}` which is shown between 2 and 6 occurrences.
 
 * it is used in `[a-z\.]{2,6}` it specifies that the TLD (Top-Level Domain) part of the email address can contain between 2 to 6 characters of lowercase letters (a-z) or dot (.)

### Character Classes
`Character classes allow the regular expression engine to match any one character from a set of characters.`
* There are several character classes defined using square brackets `[]` 

1. `[a-z0-9_\.-]` This character class matches one character that can be:

* Any lowercase letter from a to z `(a-z)` ,

* Any digit from 0 to 9 `(0-9)` ,

* Underscore `(_)` ,

* Dot `(.)` ,

* Hyphen `(-)`

So, `[a-z0-9_\.-]+` = match one or more characters of any lowercase letter, digit, underscore, dot, or hyphen.

2. `[\da-z\.-]` This character class matches one character that can be:

* Any digit `(\d)` ,
  
* Any lowercase letter from a to z `(a-z)` ,

* Dot `(.)` ,

* Hyphen `(-)`

So, `[\da-z\.-]+` = match one or more characters of any digit, lowercase letter, dot, or hyphen.

3.`[a-z\.]` This character class matches one character that can be:

* Any lowercase letter from a to z (a-z),
* Dot (.)

So, `[a-z\.]` = match one or more character of any lowercase letter, and or a dot. 

 ↪ 3 continued... `{2,6}` specifies that this character class should appear between 2 to 6 characters only (which would be for the domain name).
   
* These character classes define sets of characters that the regular expression will match against in the corresponding parts of the email address structure `(local part ("user's email name"), domain part, and TLD)` .

### Grouping and Capturing
` Groups in regular expressions are created using parentheses (), which allow you to group parts of the regex together.They also capture the text that matches the grouped pattern.`

1. Logical Grouping: It allows parts of the regex to be treated as a single part.

2. Capturing: It captures the matched text inside the parentheses so that it can be used as a resource or removed later.

* The capturing aspect in the regex expression for:`/^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/` are shown by:

- The 1st grouping being `([a-z0-9_.-]+)` where it shows the local part of the email address before the `@` symbol
- The 2nd group is the `([\da-z.-]+)` where it shows the domain part of the email address between the `@` symbol and the dot `.` before the TLD
- The 3rd group is the `([a-z.]{2,6})` where it shows TLD part of the email address after the dot `.`

* This grouping and capturing just helps in making things more simpler when breaking down this regex. Kind of like a math problem when we seperate and go step by step before solving the problem. 
### Bracket Expressions
* Bracket Expressions `[]` are used to define character classes.
* In this regex it's used by:
 
  1.`[a-z0-9_.-]+` due to using the match characters in the local part of the email address before the `@` symbol.
   -It matches lowercase letters (a-z), digits (0-9), underscore (_), dot (.), and hyphen (-).
  
  2.`[\da-z.-]+` due to the matching characters in the domain part of the email address after the `@` symbol and before the dot`.`, separator for the TLD.
  -It matches `\d` which matches any digit from (0-9)
  -It matches `a-z` which matches any lowercase letters (a-z)
  -It matches `.` dot and `-` hyphen


 3. `[a-z.]{2,6}` due to the matching characters in the top-level domain (TLD) part of the email address after the dot `.` .
  -It matches `a-z`, which matches lowercase letters (a-z)
  -Then it matches `.` dot
  
  ↪ 3 continued...`{2,6}` = that the TLD must be between 2 to 6 characters long.

* This bracket expression ensures that the regex `/^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/` will match and validate email addresses. Based on their character classes, for each specific part of an email address.



### Greedy and Lazy Match
`Greedy matching in regular expressions means that the pattern tries to match as much of the input string as possible while still allowing the entire pattern to match successfully.`

`Lazy matching in regular expressions means matching as little as possible while still meeting the pattern's requirements.`

*But this regex example expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` only uses greedy matching! because of the absence of the lazy matching quantifiers which are primarily `(+?, *?, ??, {} with ?)`.

*Whereas greedy matching means that quantifiers that it matches with are primarily `(+, *, ?, {})`.

In this regex expression example:

1. It is used with the quantifer `+` (greedy match) when matching user's email name, email service provider, and domain name(TLD).

2. Another greedy match is with the quantifer `{}` when matching `{2,6}` towards the ending of the string where the domain name is. 
## Author
 Shandy Cerda,

I am a dedicated web development student who is passionate about learning and eager to see where this journey takes me. For further insights into my work, feel free to explore my [Github profile](https://github.com/scerda8).