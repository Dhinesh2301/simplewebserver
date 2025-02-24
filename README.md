# EX01 Developing a Simple Webserver
## Date:29.02.2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
	<head>
		<title>Sample web </title>
	</head>


	<body bgcolor="brown">
	<table border="4" cellspacing="4" align="center">		
        <caption> TOP 5 REVENUE GENERATING SOFTWARE COMPANY</caption>
        <tr>
		<th>RANK</th>
		<th>COMPANY NAME</th>
		<th>SALES</th>
                <th>NATIONALITY</th>
	</tr>
		<tr>
			<td>1</td>
			<td>MICROSOFT</td>
			<td>57.9</td>
			<td>USA</td>
		</tr>

		<tr>
			<td>2</td>
			<td>ORACLE</td>
			<td>21.0</td>
			<td>USA</td>

		</tr>

		<tr>
                        
                        <td>3</td>
			<td>SAP</td>
			<td>16.1</td>
			<td>GERMANY</td>

		</tr>
                
                <tr>
                        
                        <td>4</td>
			<td>COMPUTER ASSOSIATES</td>
			<td>4.2</td>
			<td>USA</td>

		</tr>
                
                <tr>
                        
                        <td>5</td>
			<td>ADOBE</td>
			<td>3.4</td>
			<td>USA</td>

		</tr>

                
	</table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot 2024-03-12 112935.png>)
![alt text](<Screenshot 2024-03-12 112910.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
