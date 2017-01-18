
##1.1 Review and refactor


I think that the document is hard to read due to its information sequence. My suggestion to ease the comprehension of the reader would be to group the document into logic parts, following an ordered action flow something as below:<br />
<br />
1.  What is Unbabel and what are the type of texts I will be working with<br />
	* How does Unbabel work? <br />
2. Annotation tool <br />
	* what is it <br />
	* what does it do<br />
	* annotation goals<br />
	* tool quick glossary<br />
		* translation task<br />
		* batches <br />
		* etc <br />
3. User guide<br />
	* login<br />
 	* start page<br />
  	* description of what is there and how to use it<br />
 	* how to create an annotation <br />
  	* where to go<br />
  	* detail the creation of at least one of the most commons and the all the "trickiest" that may be harder to create as the spaced words<br />
  	* what are the client instructions<br />
  	* Error type and severity overview<br />
    	* mentioning that the errors details and severity are explained later on the document <br />
  	* overview do QT21 e MQM<br />
	  	* mentioning that QT21 and MQM are explained later on the document <br />
		* lista de anotations e a sua navegacao<br />
4. Descricao detalhada de<br />
	* tipos de erros <br />
	* severidade de erros<br />
	* QT21 e MQM<br />
<br />
<br />
<br />

This document is also too verbose, as in "How can I start annotating" segment<br />
I would suggest to change the document in order to put this information in sequenced bullets to ease the reading.<br />
I would also add visual support with application screenshots for each step.<br />
<br />

Lastly I would also add practical examples in errors descriptions and severity to enhance reader comprehension.<br />
<br />
<br />
<br />
##1.2 Spec out<br />
<br />
1. Login requirement specification<br />
<br />
* 1.1 - Access Page<br />
 * When the user access the application, if he is not logged in with an active session he should see the following login page:<br />
	<br />
* Mockup with the same buttons: the "contact us" and the "sign in" buttons *<br />
	<br />
   * 1.1.1 Contact us button<br />
    * If a user does not have credentials, he shall press the "Contact us" button.<br />
    * This buttol shall open a request form so that the user can manage any questions regarding login in the application directly with us.<br />

   * 1.1.2 Sign in button:<br />
    * When the user clicks on this button, the login form should be displayed:<br />
	
     * *mock up with the login form "username" and "password" labels and boxes and with a "sign in" button.*<br />
					
    * 1. Username Label - shall be defined with font XXX size XXX color FFXXXX<br />
    * 2. Password Label - shall be defined with font XXX size XXX color FFXXXX<br />
    * 3. Username shall be defined as a Textfield with font XXX size XXX color FFXXXX, with a placeholder defined as "username"<br />
    * 4. Password shall be defined as a password field with font XXX size XXX color FFXXXX with a placeholder defined as "password"<br />
    * 5. "Sign in" buton shall be defined with font XXX size XXX color FFXXXX<br />

* Flow of actions:
  * 1 - User shall fill in the username<br />
  * 2 - User shall fill in the password<br />
  * 3 - User shall press "Sign In" button<br />
	
	
	When the user press the "sign in" button web, validate if the username and password are fullfilled. 
	If any of the fields are empty display the error message: "login information is missing" with font XXX size XXX color FFXXXX
	
	If both fields are fulfilled, then perform the login request to server.
		(assuming that a login service to server is already done)
	If the login is not successful, display the error message: "login invalid" with font XXX size XXX color FFXXXX
	If the login the login is successful, redirect the user to the application welcome page (url).
	
	
 
	
#2 - Test plan <br />
### 1 - login failed <br />
#### empty username <br />
#### empty password <br />
#### empty password and username <br />
#### inexistent user <br />
#### wrong password <br />
#### sql injection <br />
 <br />
###2 - login successful <br />
#### happy path: <br />
pick a task <br />
perform annotation <br />
(1 issue minor) <br />
take a break <br />
resume annotation <br />
(1 issue minor) <br />
finnish annotation <br />
check score <br />
 <br />
#### check if QT21 is correctly calculated with 2 different issues types <br />
pick a task <br />
perform annotation <br />
(1 issue major) <br />
take a break <br />
resume annotation <br />
(1 issue minor) <br />
finnish annotation <br />
check score <br />
 <br />
#### check if QT21 is correctly calculated with 3 different issues types <br />
pick a task <br />
perform annotation <br />
(1 issue minor) <br />
take a break <br />
resume annotation <br />
(1 issue critical) <br />
take a break <br />
resume annotation <br />
(1 issue major) <br />
finnish annotation <br />
check score <br />
 <br />
#### check if QT21 is correctly calculated with 3 different issues types without breaks <br />
pick a task <br />
perform annotation <br />
(1 issue critical) <br />
finnish annotation <br />
check score <br />
 <br />

#### check if QT21 is correctly calculated with 3 different issues types with severall issues in each break session time out
pick a task <br />
perform annotation <br />
(2 issue minor) <br />
take a break <br />
resume annotation <br />
(2 issue minor) <br />
expire session <br />
login <br />
resume annotation <br />
(1 issue major) <br />
take a break <br />
resume annotation <br />
(1 issue minor) <br />
finnish annotation <br />
check score <br />
 <br />
