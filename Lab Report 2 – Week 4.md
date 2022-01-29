# Today we are going to learn about symptom, bug, failure-inducing input

## Let us start with the code changes we made in our MarkdownParse.java and MarkdownparseTest.java

![Markdownfile](https://user-images.githubusercontent.com/61016872/151638675-f8f357d8-f09f-4c77-b96b-9bfa109127ae.png)


### [Link to failure-inducing input](https://github.com/stopdatkimmy/markdown-parse/commit/efa8270d244e37c25acb8fbc0ea3e31fe47e7c90)


#### Symptom of the failure-inducing input produced by bug1.md
![symptom showing](https://user-images.githubusercontent.com/61016872/151636595-26893e6e-97fb-4aa3-89f2-ac4f26220017.png)

##### Relationship between the bug, the symptom, and the failure-inducing input

The bug in this case would be that the starter code in the MarkdownParse.java file only searches for the next close bracket or</br>
in this case **]** to look for parentheses **(** after it. So if there were no parentheses after the close bracket then the loop would</br>
never end and cause indexoutofboundsexception,symptom in this case. (So trying to find index of parentheses would result in -1 instead of positive number).
Failure inducing input in this case would be no open and closed parentheses in between the closed bracket of first link and open bracket of
second link which makes the loop to run forever. In order to finish the loop, if index of any of the bracket or parentheses were less than 0, 
we would break and end the loop.


## Second code difference- when text added after all links were found


![Text after link](https://user-images.githubusercontent.com/61016872/151638815-602b9df7-085f-4b72-9f24-3086df9bda9e.png)

### [Link to text after the link](https://github.com/bcli12/markdown-parse/commit/faf0daab51287393f18c2e72fc501216edbf9e3c#diff-c703a0ec03474d601c6bf846740b293e0538bccf38d5f677a302457479e9c652)

#### Symptom of the failure-inducing input. 


![2nd Symptom](https://user-images.githubusercontent.com/61016872/151639150-6ae62b88-97fa-4c72-af90-4815a06d458f.png)

##### Relations between bug, symptom, and input

Failure-inducing input in this case was that there was text after all the links were found, so when the all the links are found, 
currentindex would only increase by 1, and there would be failure as text is included at the end so that indexof function would 
be returning -1 for currentIndex as it can't find the open brackets after current index is increased by 1 in the original code.
Symptom is that there is not enough memory in the system so as it runs the infinite loop, it will result in error in heap space.


## Third code difference- at test file

![Screenshot 2022-01-28 162544](https://user-images.githubusercontent.com/61016872/151640312-d5d03f38-9e2a-45a9-81ec-f50202a7d78d.png)


### [Link to failure-inducing input]


![Screenshot 2022-01-28 165145](https://user-images.githubusercontent.com/61016872/151640106-0c88fb33-af5d-4b66-856f-3df433d960e1.png)

#### Symptom for third one
![Screenshot 2022-01-28 163208](https://user-images.githubusercontent.com/61016872/151640192-206c7419-958b-48ae-ac7a-99b2f1a8a830.png)

##### Relation
bug would be that the code is not testing for when there is image file, it only test for links to a certain website not for 
image so can't cpunt for exclamtion point in the middle. Failure inducing input is the image file. SYmptom would be
that the method would just be in infinite loop so it would not finish, so code runs out of heap space as memory is long gone.
SO in linke 25-27 we said if code include ! we would do openparentheses -1 to finish loop.

























