# unbabel
for challenge


yes




1.1 Review and refactor

Eu achei o documento dificil de ler devido a sequencia de informacao. A minha sugestao para facilitar a leitura seria agrupar o documento em segmentos logicos e seguindo fluxo de accoes com ordem, como por exemplo:
1 - Introducao 
		o que e a Unbabel e como funciona
2 - Annotation tool
		o que e
		para que serve 
		objectivo de uma annotation
		introducao aos termos usados na tool
			- task de traducao
			- batches
			- etc
3 - User guide
		login
		pagina inicial
			descricao do que ha e como usar
		como criar uma annotation 
			onde ir
			(indicacao que o detalhe dos erros, a severidade dos erros e descricao detalhada do que e o QT21 e MQM estao mais a frente)
			detalhar a criacao de annotations pelo menos uma das mais comuns e as menos comuns que possam ser mais dificeis de criar (duas palavras espacadas)
			o que sao as instrucoes do cliente
			overview dos tipos de erros e da severidade
			overview do QT21 e MQM
		lista de anotations e a sua navegacao

4 - Descricao detalhada de
			-tipos de erros 
			-severidade de erros
			-QT21 e MQM
	


Este documento esta muito verboso como por exemplo no trecho "How can I start annotating"
Eu mudaria o documento de forma a por esta informacao em forma de bullets sequenciados para facilitar a leitura.
Tambem adicionaria apoio visual com um screeshot da aplicacao para cada step.



Tambem adicionaria exemplos praticos na descricao do tipo e severidade dos erros para ser mais perceptivel ao utilizador final.



1.2 Spec out

1 - Login requirement specification

1.1 - Access Page
	When the user access the application, if he is not logged in with an active session he should see the following login page:
	
	Mockup with the same buttons: the "contact us" and the "sign in" buttons
	
1.1.1 Contact us button
	If a user does not have credentials, he shall press the "Contact us" button.
	This buttol shall open a request form so that the user can manage any questions regarding login in the application directly with us.

1.1.2 Sign in button:
	When the user clicks on this button, the login form should be displayed:
	
	mock up with the login form "username" and "password" labels and boxes and with a "sign in" button.
	1 - Username Label - shall be defined with font XXX size XXX color FFXXXX
	2 - Password Label - shall be defined with font XXX size XXX color FFXXXX
	3 - Username shall be defined as a Textfield with font XXX size XXX color FFXXXX, with a placeholder defined as "username"
	4 - Password shall be defined as a password field with font XXX size XXX color FFXXXX with a placeholder defined as "password"
	5 - "Sign in" buton shall be defined with font XXX size XXX color FFXXXX

	Flow of actions:
	1 - User shall fill in the username
	2 - User shall fill in the password
	3 - User shall press "Sign In" button
	
	
	When the user press the "sign in" button web, validate if the username and password are fullfilled. 
	If any of the fields are empty display the error message: "login information is missing" with font XXX size XXX color FFXXXX
	
	If both fields are fulfilled, then perform the login request to server.
		(assuming that a login service to server is already done)
	If the login is not successful, display the error message: "login invalid" with font XXX size XXX color FFXXXX
	If the login the login is successful, redirect the user to the application welcome page (url).
	
	
 
	
2 - Test plan <br />
1 - login failed <br />
empty username <br />
empty password <br />
empty password and username <br />
inexistent user <br />
wrong password <br />
sql injection <br />
 <br />
2 - login successful <br />
happy path: <br />
pick a task <br />
perform annotation <br />
(1 issue minor) <br />
take a break <br />
resume annotation <br />
(1 issue minor) <br />
finnish annotation <br />
check score <br />
 <br />
check if QT21 is correctly calculated with 2 different issues types <br />
pick a task <br />
perform annotation <br />
(1 issue major) <br />
take a break <br />
resume annotation <br />
(1 issue minor) <br />
finnish annotation <br />
check score <br />
 <br />
check if QT21 is correctly calculated with 3 different issues types <br />
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
check if QT21 is correctly calculated with 3 different issues types without breaks <br />
pick a task <br />
perform annotation <br />
(1 issue critical) <br />
finnish annotation <br />
check score <br />
 <br />

check if QT21 is correctly calculated with 3 different issues types with severall issues in each break session time out
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
