# EX01 Developing a Simple Webserver
## Date:17.04.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler 
content="""
<html>
<title>TCP/IP PROTOCOL</title>
<body>
<table border="2" align="center">
<caption>TCP/IP PROTOCOL SUITE</caption>
<br>
<tr bgcolor="pink">
<th>S.No</th><th>LAYER</th><th>PROTOCOLS</th>
</tr> <tr>
<td>1</td><td>Application Layer</td><td>HTTP,FTP,DNS,Telnet,SSH</td>
</tr>
<tr>
<td>2</td><td>Transport Layer</td><td>TCP,UDP</td>
</tr>
<tr>
<td>3</td><td>Internet Layer</td><td>ICMP,IGMP,ARP,IPv4/IPv6</td>
</tr>
<tr>
<td>4</td><td>Network Access Layer</td><td>MAC/Ethernet,FDDI,Frame Relay</td>
</tr>
</table>
</body>
</html>
"""
class myhandler (BaseHTTPRequestHandler):
     def do_GET(self):
        print("request received") 
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![Screenshot 2025-05-13 140653](https://github.com/user-attachments/assets/3d32bf43-b122-48c6-a13e-2fdfab321bce)
![Screenshot 2025-05-13 140738](https://github.com/user-attachments/assets/4fa11ccd-b7d1-42e7-a9b0-ce7131379443)


## RESULT:
The program for implementing simple webserver is executed successfully.
