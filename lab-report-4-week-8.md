# Lab-report-4-week-8

## In this assignment, we will learn further about how testing and debugging works with VSCODE

### 1. Link to my markdown-parse repository: https://github.com/stopdatkimmy/markdown-parse

### 2. Link to other group's markdownparse repository: https://github.com/TheZenMasterz/markdown-parse

#### Snippet 1.
VS code preview
![Screenshot 2022-02-25 023452](https://user-images.githubusercontent.com/61016872/155700570-f1a81c7e-9b52-4592-85d7-1b76f939a345.png)

Test added on MarkdownParseTest.java
![Screenshot 2022-02-27 173426](https://user-images.githubusercontent.com/61016872/155910348-9e679d4d-31dc-453a-888d-35ce29c570a4.png)

**My implementation result**

![Screenshot 2022-02-27 173849](https://user-images.githubusercontent.com/61016872/155910580-d7abbdf9-d474-4064-91d9-4e6a8be6238c.png)

**Other group review result**

![Screenshot 2022-02-27 174950](https://user-images.githubusercontent.com/61016872/155911376-b1e955dd-fdf4-44e0-b368-e823da29bf82.png)

Both implementation do not pass.

#### Snippet 2
VS code preview
![Screenshot 2022-02-27 182337](https://user-images.githubusercontent.com/61016872/155913884-9afa2894-b6d6-41a7-af68-8427bf8f9083.png)

Test added on MarkdownParseTest.java
![Screenshot 2022-02-27 185147](https://user-images.githubusercontent.com/61016872/155916128-7bda4897-d991-4070-a3b0-68b6f77dd24a.png)


**My implementation result**
![Screenshot 2022-02-27 182824](https://user-images.githubusercontent.com/61016872/155914159-6bc2d533-4b88-435b-8355-db088c01f778.png)

**Other group review result**
![Screenshot 2022-02-27 182936](https://user-images.githubusercontent.com/61016872/155914247-5cfcfcb2-713f-415d-a1df-96d162c02043.png)

Both implementation do not pass

#### Snippet 3

VS code preview
![Screenshot 2022-02-27 185036](https://user-images.githubusercontent.com/61016872/155916033-07bf348b-0c4d-4661-8370-6c7e8306e084.png)

Test added on MarkdownParseTest.java

![Screenshot 2022-02-27 185522](https://user-images.githubusercontent.com/61016872/155916450-78a6ec5b-5047-4af8-bd1f-32d447c942ed.png)

**My implementation result**

![Screenshot 2022-02-27 185636](https://user-images.githubusercontent.com/61016872/155916584-c18d4256-0c6a-48ec-8d13-700554ddd77a.png)

**Other group review result**
![Screenshot 2022-02-27 185757](https://user-images.githubusercontent.com/61016872/155916722-0683325a-bdbf-44bc-9d5a-027e89c0ac39.png)

And again, Both implementation do not work



### Answer the following questions with 2 or 3 sentences each
1. Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? 
If yes, describe the code change. If not, describe why it would be a more involved change.

I do not think that there could be a small code change for it to work for snippet 1 with inline ocde with backticks. One way to solve this problem would be to 
preprocess string by removing regions that have backtick formatted code in them. However, it will require much more lines to change rather than just fixing less than 10 lines.

**public static String removeCode(String markdown) {<br>
	Pattern p = Pattern.compile("`+");<br>
	Matcher m = p.matcher(markdown);<br>
	int maxlen = 0;<br>
	while (m.find())` {`[a link`](url.com)<br>
  [another link](`google.com)<br>
  [`cod[e`](google.com)<br>
  [`code]`](ucsd.edu)<br>
  maxlen = Math.max(m.group(0).length(), maxlen);<br>
	}<br>
	String fin = markdown;<br>
	for (int i = maxlen; i >= 1; i--) {<br>
		Pattern pp = Pattern.compile("`{"+i+"}.*?`{"+i+"}", Pattern.DOTALL | Pattern.MULTILINE);<br>
		fin = pp.matcher(fin).replaceAll("");<br>
	}<br>
	return fin;<br>
}**<br>

2. Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.

<p>No because I think it would be more of a involved change where we would have to check for number of nested parentheses within the links.<br>
For example, if we look at [a [nested link](a.com)](b.com)
only the inner-most definition of links are used, so a.com is produced. So we would have to check for number of brackets in the links and remove those within, which would not
be enough for less than 10 lines of code. We might have to do something like<br>
 
for(int i = 0;i<array.length;i++){
//remove all the brackets within the nested loop}
Same goes for escape brackets and nested parenthesized url. For nested url, cannot find the next closebracket if there are more than one open brackets.
So just change the code so that in line 32 insert case when substring.contains("(") to add all the nested parentheses.
For escaped brackets, just remove escaped brackets.



  
	
3. Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.

I think in case when there is newlines in brackets and parentheses, we would have to try and catch "\n" and break the code.<br> 
so either do **if(nextopenbracket=="\n"){break;}** or try to catch just the links that are lines below the brackets.
`if(nextcloseBracket+1 !=nextOpenparen){
continue};
if(nextOpenparen+1 !=nextCloseparen){continue};`
to keep finding open and close paren, next closed bracket to resolve the issue.









