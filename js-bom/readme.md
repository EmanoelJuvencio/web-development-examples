# The Browser Object Model

O BOM (Browser Object Model) é uma forma da Linguagem Javascript obter informações e controlar o browser.
Mesmo existindo há muito tempo, não existe um padrão para manipular o BOM.
A maioria dos browsers disponiliza os mesmo métodos e propriedades BOM, mas em alguns casos existem diferenças sutis.

Os principais objetos disponíveis para manipulação do Browser são:
* window -> representa a janela do navegador
* screen -> provê informações da tela do sistema operacional
* location -> provê informações da url
* history -> controla o histórico de navegação
* navigator -> provê informações do navegador

## window

A principal informação disponível é o tamanho da janela: 
+ window.innerHeight: Altura 
+ window.innerWidth: Largura

No caso do IE (8 ou inferior):
+ document.documentElement.clientHeight (ou document.body.clientHeight)
+ document.documentElement.clientWidth (ou document.body.clientWidth)

Uma solução abrangente pode ser
+ var w = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth;
+ var h = window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight;

Alguns outros métodos interessantes são:
+ window.open() - abre uma nova janela
```javascript
	win = window.open('http://google.com.br', '', 'width=200, height=100');
```
+ window.close() - fecha uma janela
+ window.moveTo() - move a janela
+ window.resizeTo() - altera as dimensões
+ window.focus() - ativa o foco da janela
+ window.location - modifica o documento aberto na janela

screen
======

Window Screen
Pode ser acessado por window.screen ou apenas screen.

Properties:

screen.width
screen.height
screen.availWidth
screen.availHeight
screen.colorDepth
screen.pixelDepth

location
========
Acessado por window.location.

Some examples:
window.location.href returns the href (URL) of the current page
window.location.hostname returns the domain name of the web host
window.location.pathname returns the path and filename of the current page
window.location.protocol returns the web protocol used (http: or https:)
window.location.assign loads a new document

Example
Display the href (URL) of the current page:

document.getElementById("demo").innerHTML =
"Page location is " + window.location.href;
Result is:

Page location is https://www.w3schools.com/js/js_window_location.asp 
Try it Yourself »
Window Location Hostname
The window.location.hostname property returns the name of the internet host (of the current page).

Example
Display the name of the host:

document.getElementById("demo").innerHTML =
"Page hostname is " + window.location.hostname;
Result is:

Page hostname is www.w3schools.com
Try it Yourself »

Window Location Pathname
The window.location.pathname property returns the pathname of the current page.

Example
Display the path name of the current URL:

document.getElementById("demo").innerHTML =
"Page path is " + window.location.pathname;
Result is:

/js/js_window_location.asp
Try it Yourself »
Window Location Protocol
The window.location.protocol property returns the web protocol of the page.

Example
Display the web protocol:

document.getElementById("demo").innerHTML =
"Page protocol is " + window.location.protocol;
Result is:

Page protocol is https:
Try it Yourself »
Window Location Port
The window.location.port property returns the number of the internet host port (of the current page).

Example
Display the name of the host:

document.getElementById("demo").innerHTML =
"Port number is " + window.location.port;
Result is:

Port name is
Try it Yourself »
Most browsers will not display default port numbers (80 for http and 443 for https)

Window Location Assign
The window.location.assign() method loads a new document.

Example
Load a new document:

<html>
<head>
<script>
function newDoc() {
    window.location.assign("https://www.w3schools.com")
}
</script>
</head>
<body>

<input type="button" value="Load new document" onclick="newDoc()">

</body>
</html>
Try it Yourself »


history
=======
JavaScript Window History
❮ PreviousNext ❯
The window.history object contains the browsers history.

Window History
The window.history object can be written without the window prefix.

To protect the privacy of the users, there are limitations to how JavaScript can access this object.

Some methods:

history.back() - same as clicking back in the browser
history.forward() - same as clicking forward in the browser


browser
=======
JavaScript Window Navigator

The window.navigator object contains information about the visitor's browser.

Window Navigator
The window.navigator object can be written without the window prefix.

Some examples:

navigator.appName
navigator.appCodeName
navigator.platform
Browser Cookies
The cookieEnabled property returns true if cookies are enabled, otherwise false:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"cookiesEnabled is " + navigator.cookieEnabled;
</script>
Try it Yourself »
Browser Application Name
The appName property returns the application name of the browser:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"navigator.appName is " + navigator.appName;
</script>
Try it Yourself »
Strange enough, "Netscape" is the application name for both IE11, Chrome, Firefox, and Safari.


Browser Application Code Name
The appCodeName property returns the application code name of the browser:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"navigator.appCodeName is " + navigator.appCodeName;
</script>
Try it Yourself »
"Mozilla" is the application code name for both Chrome, Firefox, IE, Safari, and Opera.

The Browser Engine
The product property returns the product name of the browser engine:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML =
"navigator.product is " + navigator.product;
</script>
Try it Yourself »
The Browser Version
The appVersion property returns version information about the browser:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.appVersion;
</script>
Try it Yourself »
The Browser Agent
The userAgent property returns the user-agent header sent by the browser to the server:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.userAgent;
</script>
Try it Yourself »
Warning !!!
The information from the navigator object can often be misleading, and should not be used to detect browser versions because:

Different browsers can use the same name
The navigator data can be changed by the browser owner
Some browsers misidentify themselves to bypass site tests
Browsers cannot report new operating systems, released later than the browser
The Browser Platform
The platform property returns the browser platform (operating system):

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.platform;
</script>
Try it Yourself »
The Browser Language
The language property returns the browser's language:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.language;
</script>
Try it Yourself »
Is The Browser Online?
The onLine property returns true if the browser is online:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.onLine;
</script>
Try it Yourself »
Is Java Enabled?
The javaEnabled() method returns true if Java is enabled:

Example
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = navigator.javaEnabled();
</script>
Try it Yourself »

