
# 1.1 - Review and refactor


I think that the document is hard to read due to its information sequence. My suggestion to ease the comprehension of the reader would be to group the document into logic parts, following an ordered action flow something as below:

#### 1.  What is Unbabel and what are the type of texts I will be working with 
* How does Unbabel work?  

<br />
#### 2. Annotation tool <br />
* what is it 
* what does it do
* annotation goals
* tool quick glossary
	* translation task
	* batches 
	* etc   
	
<br />
#### 3. User guide<br />
* login
* start page
* description of what is there and how to use it
* how to create an annotation 
	* where to go
	* detail the creation of at least one of the most commons and the all the "trickiest" that may be harder to create as the spaced words
	* what are the client instructions
	* Error type and severity overview
		* mentioning that the errors details and severity are explained later on the document 
	* overview do QT21 e MQM
		* mentioning that QT21 and MQM are explained later on the document
	* lista de anotations e a sua navegacao  
	
#### 4. Detailed description of
* error types
* error severity
* QT21 e MQM
<br />
<br />
<br />

This document is also too verbose, as in "How can I start annotating" segment<br />
I would suggest changing the document in order to put this information in sequenced bullets to ease the reading.<br />
I would also add visual support with application screenshots for each step.<br />
<br />

Lastly I would also add practical examples in errors descriptions and severity to enhance reader comprehension.
<br />
<br />
<br />
# 1.2 Spec out
<br />
#### 1. Login requirement specification<br />
<br />
#### Access Page
When the user accesses the application, if he is not logged in with an active session he should see the following login page:
<br />
		(Mockup with the same buttons: the "contact us" and the "sign in" buttons)
###### Fields description
1. Contact Us - shall be defined with font XXX size XXX color FFXXXX
2. Sign in - shall be defined with font XXX size XXX color FFXXXX		

##### Contact us button
If a user does not have credentials, he shall press the "Contact us" button.
This button shall open a request form so that the user can manage any questions regarding login in the application directly with us.

##### Sign in button:>
When the user clicks on this button, the login form should be displayed:
<br />
	(mock up with the login form "username" and "password" labels and boxes and with a "sign in" button)
###### Fields description
1. Username Label - shall be defined with font XXX size XXX color FFXXXX
2. Password Label - shall be defined with font XXX size XXX color FFXXXX
3. Username shall be defined as a Textfield with font XXX size XXX color FFXXXX, with a placeholder defined as "username"
4. Password shall be defined as a password field with font XXX size XXX color FFXXXX with a placeholder defined as "password"
5. "Sign in" buton shall be defined with font XXX size XXX color FFXXXX

#### Flow of actions:
1. User shall fill in the username
2. User shall fill in the password
3. User shall press "Sign In" button
	
	
#### When the user presses the "sign in" button web, validate if the username and password are fullfilled. 
If any of the fields are empty display the error message: "login information is missing" with font XXX size XXX color FFXXXX
If both fields are fulfilled, then perform the login request to server. (assuming that a login service to server is already done)
	If the login is not successful, display the error message: "login invalid" with font XXX size XXX color FFXXXX
	If the login the login is successful, redirect the user to the application welcome page (url).
