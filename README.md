
Bootcamp Challenge 17

# Regex Tutorial - Matching an Email

Below is a gist tutorial for matching an email using regex. This can be important for applications or users that need to match and validate email addresses quickly. Hope you enjoy!

## Summary

The regex that I will be describing in this tutorial is 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

## Table of Contents

- [Regex Literal](#regex-literal)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions and Character Classes](#bracket-expressions-and-character-classes)
- [Literals](#literals)
- [Back-references](#back-references)
- [Author](#author)

## Regex Literal

Regular expressions are literals, and like other literals must begin with a 
```
/
```
and end with
```
\
```

Hence, since it is a literal, each character will be searched exactly like it is written.

## Anchors

The second component of our regex statement that we need to look at is our anchors. 

Our opening anchor is 
````
^
````
That should be our second character in our regex statement.


Our closing anchor is 
````
$
````
That should be our second to last character in our regex statement. 


So our regex statement would look like this so far:
````
/^ (string) $/
````

The opening and closing anchor contain a string within them. This could be formatted in one of two ways. 

  The first way is 
  ```` 
  /^ "food" $/ 
  ```` 
  This would look for an exact string match for 
  ```
  "food"
  ```
  and would not produce a match for 
  ``` 
  "Food"
  ```
  because the F is capitilized.

  The second way is to use bracket expression [ ]. Now, the brackets signify a range of characters rather than an exact match. So if we had 
  ```
  /^ [food] $/
  ```
  This would look for a string that includes the letters f,o,o,d. So the following would all produce a match
  ```
  "ferrari" "orange" "deer"
  ```
  since each one of these strings contains one of the letters within the brackets.

Now that we have the basics of how to start and end our regex statement, let's take a deep dive into our regex statement that will allow a user to match an email.

## Quantifiers

Quantifiers are special characters that identify how many times a character(s) should appear in the match.

So in our entire regex statement: 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
We have 3 quantifiers.

Our first quantifier is 
```
the + in ([a-z0-9_\.-]+)
```
The + quantifier is used to indicate that our matched email should contain at least 1 or more of the characters within the brackets preceding it. We will go over the characters that are being used to match the email in the [Bracket Expressions and Character Classes](#bracket-expressions-and-character-classes) section. 

Our second quantifier is 
```
the + in ([\da-z\.-]+)
```
The + quantiifer in this grouping indicates that our matched email must contain at least 1 or more of the characters within the brackets preceding it. Again, we will go over the characters that are being used to match the email in the [Bracket Expressions and Character Classes](#bracket-expressions-and-character-classes) section. 

Our last quantifier is 
```
the {2,6} in ([a-z\.]{2,6})
```
This quantifier that appears sets the minimum and maximum length of our email being matched. The 2 represents the minumum length and the 6 represents the maximum length that this grouping in our expression must match. We will go over the other character in the [Bracket Expressions and Character Classes](#bracket-expressions-and-character-classes) section. 

## Grouping and Capturing

Grouping constructs are ways to group sections of our regex statement. Sections of our regex statement that are wrapped in
```
( )
```
represent different groupings constructs.

In our matching an email regex
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
we have 3 grouping constructs
```
([a-z0-9_\.-]+)
```
```
([\da-z\.-]+)
```
```
([a-z\.]{2,6})
```

## Bracket Expressions and Character Classes 

Bracket expressions are the parts of regex that are enclosed within
```
[]
```
Within the bracket expressions, we have character classes that allow us to match the characters that might appear in our email. 

In our regex
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
we have 3 bracket expressions.

```
[a-z0-9_\.-] in ([a-z0-9_\.-]+)
```
This bracket expression, searches for a match that has lowercase letters from a to z, numbers from 0 to 9, and matches for underscores _. The \ escapes the special meaning of the . so we can search for a . and the - will search for matches with a - (hyphen.)

This bracket expression matches the part of the email that comes before the @ symbol.

```
[\da-z\.-] in ([\da-z\.-]+)
```
The \d will match any digit. The a-z will match any lowercase letter from a to z. The \ before the . will escape the special notation of the . and allow us to look for matches for the period itself. It will also look for hyphen (-) matches.

This bracket expression matches the part of the email that comes after the @ symbol.

```
[a-z\.] in ([a-z\.]{2,6})
```
Within this bracket expression, we are searching for a match that has lowercase letters from a to z. The \ in the \. escapes the special meaning of the dot in regex so we can search for the . in our email. 

This bracket expression matches the part of the email that comes after the '.'   . 


## Literals

In our regex
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
we have 2 literal characters

```
@ that seperates the first 2 bracket expressions.
```
and 
```
\. that seperates the last 2 bracket expressions.
```
The @ symbol mathces the @ symbol in emails and the . matches the period that comes before the com or net in an email.

## Back-references
```
https://www.youtube.com/watch?v=7DG3kCDx53c
https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial
```

## Author

My name is Nathan Difiori and I am currenlty a UCI Fullstack Bootcamp student. Here is a link to my Github. Please feel free to reach out to me: ndifiori@gmail.com .

Here is my [Github Repo](https://github.com/ndifiori?tab=repositories).