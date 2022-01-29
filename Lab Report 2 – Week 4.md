# Today we are going to learn about symptom, bug, failure-inducing input

## Let us start with the code changes we made in our MarkdownParse.java and MarkdownparseTest.java

![Markdownparse file](https://user-images.githubusercontent.com/61016872/151635801-c898257c-84e6-4cb3-8b1c-2991b6ceee58.png)

### [Link to failure-inducing input](https://github.com/stopdatkimmy/markdown-parse/commit/efa8270d244e37c25acb8fbc0ea3e31fe47e7c90)


#### Symptom of the failure-inducing input produced by bug1.md
![symptom showing](https://user-images.githubusercontent.com/61016872/151636595-26893e6e-97fb-4aa3-89f2-ac4f26220017.png)

##### Relationship between the bug, the symptom, and the failure-inducing input

The bug in this case would be that the starter code in the MarkdownParse.java file only searches for the next close bracket or</br>
in this case **]** to look for parentheses **(** after it. So if there were no parentheses after the close bracket then the loop would</br>
never end and cause indexoutofboundsexception. (So trying to find index of parentheses would result in -1 instead of positive number).
Failure inducing input in this case would be no open and closed parentheses in between the closed bracket of first link and open bracket of
second link which makes the loop to run forever. In order to finish the loop, if index of any of the bracket or parentheses were less than 0, 
we would break and end the loop.



















