# **Lab Report - Week 4**

## For this lab we looked at the file MarkdownParse.java and make changes to pass the following test cases:

```
Test 1: was a normal link with parenthesis inside it.
 -goog()le.com

Test 2: was a normal link, and one lacking the end parenthesis.
 -[a-link] (www.google.com
 -[Lab Report 1](lab-report-1-week-2.html)

Test 3:
 -was an empty file
 ```

 The first change done was the one that follows:

![Image](first_change.png)

> Here is the link to the first test: [Test 1](https://github.com/Ironhide692/markdown-parse/blob/e20013ee9242b37aeccf6be73826b85c85c9a84c/breaking-test.md)

For this test the following result was returned in the terminal:

```
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
    at java.base/java.util.Arrays.copyOfRange(Arrays.java:3822)
    at java.base/java.lang.StringLatin1.newString(StringLatin1.java:769)
    at java.base/java.lang.String.substring(String.java:2709)
    at MarkdownParse.getLinks(MarkdownParse.java:24)
    at MarkdownParse.main(MarkdownParse.java:33)
```

