# EX01 Developing a Simple Webserver
## Date:

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
<head>
</head>
<body>
    <h1>LAPTOP CONFIGURATION</h1>
    <table border="2" cellpadding="10">
        <tr>
            <th>Property</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>lidison sham</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00342-42708-86811-AAOEM00342-42708-86811-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',5000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/1043db61-6123-4c10-939b-d07bbdaa2e49)


## RESULT:
The program for implementing simple webserver is executed successfully.
