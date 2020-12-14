# Regex for Matching an Email

In this gist we are going to explain the use of a Regex, such as `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` which can be used to match emails. This is especially  useful when you need to validate emails using packages like MongoDb or Inquirer.

## Summary

Wikipedia defines a Regular Expression, Regex for short, as "a sequence of characters that define a search pattern." This is commonly used for input validation, to find patterns within a string, find/replace characters within a string. Regular Expressions have many uses. However here we will go through how the components of this regex applies to matching an email. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors  

This Regex uses the Anchors `^ ` and `$`.   

The Anchor `^ ` is used to specify the beginning of the string and `$` to specify the ending of the string. Since the multiline option is not enabled,`(m)`, the regex will end at `$`.

### Quantifiers  

This Regex uses the Quantifier `+`and `{}`.  
  
In this instance,`+`, will join the users email name + email provider + `.com`. The other being `{2,6}`, which allows a match to range from 2-6 characters and provides a character set, more on these shortly, of `[a-z\.]`.

### Character Classes  

This Regex only contains one Character Class `\d`  
  
Which is used to match a single character that is a digit from 0-9. This will only match a single digit such as 7. It does not allow for multiple digits like 777. 

### Grouping and Capturing  
  
This Regex has 3 Groupings.  

The first Grouping used here is `([a-z0-9_\.-]+)` which matches the user's "email name".  
  
The second Grouping is `([\da-z\.-]+)` which matches the "email provider".  
  
Finally we have the third Grouping `([a-z\.]{2,6})` to capture the `.com`.

### Bracket Expressions  

Thinking back to the Groupings we had a few Bracked Expressions in this Regex.  
  
The first Grouping had the Bracked Expression of `[a-z0-9_\.-]`. This is used to match any case senstive letter a-z, any character 0-9, and lastly it matches the characters '_', '.' and '-'.  

The second Grouping had the Bracked Expression of `[\da-z\.-]`. This is used to match any single digit from 0-9, any case senstive letter a-z, but this time only the extra characters "." and "-".    

Lastly the third Grouping `[a-z\.]` is going to match any case senstive letter a-z and only the extra character ".". 

### Greedy and Lazy Match  

This Regrex does include Greedy Matches.  
  
The quantifiers `+` and `{}` are greedy operators, they are going to expand the match as far as they can through the provided text. `+` is going to match as many times as possible, giving back as needed. The other Quantifier used in this regex is `{}` when matching `{2,6}` for the last capture group.

## Author  

Come take a look at any of my other projects at https://github.com/TPino92 !