# REGEX TUTORIAL: Matching an Email

A regular expression, also referred to as **Regex**, is a sequence of characters that defines a specific search pattern. Think about the <u>Find</u> feature that many applications and websites offer. You would start with *Control + F*, and then type what you want to look for in the document or text. This feature will scan through the text/page and highlight all the occurances where it finds exactly what you typed. In a similar manner, a regex forms a search pattern that is used to locate and/or validate specific strings either in a sentence, a document, or any other character input.

## Summary

To better understand how a regex works, we'll take a look at a regular expression used for matching an email. This is a helpful application that is utilized in online form validations since each component of this regex is responsible for creating a pattern to ensure that the user enters an email address. This means that it is checking for an unspecified number of characters, followed by the ` @ ` , followed by a domain. The syntax for this regular expression is:

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

---

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)

<br>

## Regex Components

### **Anchors**

When you read through the regular expression, the first thing that follows the forward slash (which we will discuss in the [Boundaries](#boundaries) section), is the caret anchor ` ^ ` and the regex ends with  the dollar anchor ` $ ` . The caret anchor ` ^ ` indicates the current position in the string is the beginning of the string, while the dollar anchor ` $ ` indicates the end of a string/line.

### **Quantifiers**

Quantifiers in a regex indicate the number of characters or expressions to match. This can be seen near the end of our regular expression: `{2,6}`. The 2 and the 6 are setting the minimum and maximum matches of the preceding item, which in this case is refering to the `[a-z\.]`. When looking at an email domain, after the dot `.` you'll typically see "co", "com", "org", etc. The quantifier is checking that there are at least 2 matches, but no more than 6.

Another quantifier that we see is the `+`. The regular expression adds on to the match, one character after another. This will continue to repeat until there is no longer a match in the preceding character, which would be the bracket expressions (i.e. `[a-z0-9_\.-]`).


### **Character Classes**

Character classes, also known as *bracket lists*, are used to distinguish between different kinds of characters, such as letter and digits. There can be single characters inside the brackets, or we can use the hyphen as shorthand for adding a range of characters. A couple examples of character classes that we see in our regular expression are:

- `[a-z0-9_\.-]`: This is looking to match with any lowercase letter from a to z, any number 0-9, an underscore, a dot `.`, and a hyphen.

- `[\da-z\.-]` : The `\d` will match with any single digit (equivalent to `[0-9]` in most cases). The rest of the character class will look for any lowercase letter from a to z, a dot `.` and a hyphen.

### **Grouping and Capturing**

Parantheses `( )` are used to group sub-expressions for applying a repetition operator. In this regex, we see that the bracket expressions `[]` and repetition operators `+`/`{}` are inside the parantheses to separate each separate expression.

### **Bracket Expressions**

Brackets expressions are a set of characters inside of brackets `[ ]`, and are also known as a character class. For example, `[abc]` that is the same as `[a-c]`. Both will match the "b" in "boy", and the "c" in "colorful". We can see 3 separate bracket expressions in our regular expression. It's helpful to a hyphen inside of brackest to indicate a range of characters. There are some special characters that need to be "escaped" first before they can be used as they are. Those characters include: `() [] {} ^ $ . | * + ? \`. In order to use them, you need to include a `\` first; therefore you'll have: `^`, `\-`, `\]`, `\\`. This is also why we see `\.` when it is matching for a dot/period `.` instead of its special function.

### **Greedy and Lazy Match**

For this example, we are able to find a repetition operator (`+`), also known as *greedy operators* because they repeat as many times as possible.

### **Boundaries**

In a regular expression, a forward slash ( / ) is used to set the boundary. This can be seen at the beginning and end of the regex for matching an email. 

## **Author**

Emilio Acosta, beginner Full-Stack Web Developer. [GitHub Link](https://github.com/EmilioAcostaG)