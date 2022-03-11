# **Lab Report - Week 10 :)**

## In this weeks report we will:
Compare the implimentation of my MarkdownParse and the one provided in lab 9. I will compare two test and see the different outut that each implementation shows. To find these test I just searched for intereting test cases manually.

---

### First test case:
>Test 182

```
<![CDATA[
function matchwo(a,b)
{
    if (a < b && a < 0) then {
        return 1;
    } else {


        return 0;
    }
}
]]>
okay
```
In this test case the output from my version of MarkdownParse resulted in this: 


```
[<![CDATA>[
function matchwo(a,b]
```
and the output from the provided implementation in this:
```
[]
```
For this test the correct implementation is the one provided.  The expected output should be empty. 
To fix this we have to add an if statement that looks if openParen is -1 and break the loop if that is the case.

```
if(openParen == -1) break;
toReturn.add(markdown.substring(openParen + 1, closeParen));
```

### Second test case:
>Test 489

```
[link](foo
bar)
```

In this test case the output from my version of MarkdownParse resulted in this: 

```
[foo
bar]
```

and the provided implementation in this:

```
[]
```
For this the correct implementation was also the one provided. The expected output shuld be empty since it continues in a new line, therefore, not making it a valid link. To fix this we have to add an if statement that checks for new lines.

```
 if (toAdd.contains("\n")) {
     closeParen = markdown.indexOf("\n", openParen);
     toAdd = markdown.substring(openParen + 1, closeParen).trim();
     }
```




