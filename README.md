# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display top five Programming Languages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver
## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<h1><b>TOP FIVE PROGRAMMING LANGUAGES</b></h1>
</head>
<body>
<h2>1.JAVASCRIPT</h2>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/2048px-Unofficial_JavaScript_logo_2.svg.png" height="100" width="100">
<ul>
    <li>Designed by: Brendan Eich of Netscape.</li>
    <li>First appeared: December 4, 1995; 25 years ago.</li>
    <li>JavaScript is the dominant client-side scripting language of the Web, with 97 percent of websites using it for this purpose.</li>
    <li> It has dynamic typing, prototype-based object-orientation and first-class functions.</li>
    <li>As a multi-paradigm language, JavaScript supports event-driven, functional, and imperative programming styles.</li>
</ul>
<h2>2.PYTHON</h2>
<img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM-flattened.png" height="100" width="150">
<ul>
    <li>Designed by: Guido van Rossum.</li>
    <li>First appeared: February 20, 1991; 30 years ago.</li>
    <li>Python is dynamically-typed and garbage-collected.</li>
    <li>It supports multiple programming paradigms, including structured (particularly, procedural), object-oriented and functional programming.</li>
    <li>It can also serve as a scripting language for web applications.</li>
</ul>
<h2>3.C PROGRAMMING</h2>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/C_Programming_Language.svg/695px-C_Programming_Language.svg.png" height="100" width="100">
<ul>
    <li>Designed by: Dennis Ritchie.</li>
    <li>First appeared: 1972; 49 years ago.</li>
    <li>It is a general-purpose, procedural computer programming language supporting structured programming, lexical variable scope, and recursion, with a static type system.</li>
    <li>By design, C provides constructs that map efficiently to typical machine instructions.</li>
    <li>The type system in C is static and weakly typed, which makes it similar to the type system of ALGOL descendants such as Pascal.</li>
</ul>
<h2>4.C++ PROGRAMMING</h2>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ISO_C%2B%2B_Logo.svg/1200px-ISO_C%2B%2B_Logo.svg.png" height="100" width="100">
<ul>
    <li>Designed by: Bjarne Stroustrup.</li>
    <li>Stable release:15 December 2020; 11 months ago.</li>
    <li>C++ now has object-oriented, generic, and functional features in addition to facilities for low-level memory manipulation.</li>
    <li>It is almost always implemented as a compiled language.</li>
    <li>C++ has also been found useful in many other contexts, with key strengths being software infrastructure and resource-constrained applications.</li>
</ul>
<h2>5.R LANGUAGE</h2>
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ21yXHl4LI3S9BCTbxr9bwb9y5X7kne9yI9mDvJelzZCs4Tb-pIrmARfItspX4ovCIOm8&usqp=CAU" height="100" width="150">
<ul>
    <li>Designed by: Ross Ihaka, Robert Gentleman.</li>
    <li>First appeared: August 1993; 28 years ago.</li>
    <li>It is widely used among statisticians and data miners for developing statistical software and data analysis.</li>
    <li>It is procedural, object-oriented, functional, reflective and imperative programming language</li>
    <li>R is an interpreted language; users typically access it through a command-line interpreter.</li>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![CLIENT SIDE OUTPUT](C:\Users\Rithigasri\Pictures\OUTPUT1.png)


## RESULT:
