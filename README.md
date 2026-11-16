# EX01 Developing a Simple Webserver
## Date:14/11/26
## REG NO:26009503

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


~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>Network Protocols</title>
</head>
<body>
<h1>List of Network Protocols</h1>

<table border="1" cellpadding="10">
    <tr>
        <th>S.No</th>
        <th>Protocol</th>
        <th>Full Form</th>
        <th>Description</th>
    </tr>

    <tr>
        <td>1</td>
        <td>HTTP</td>
        <td>Hypertext Transfer Protocol</td>
        <td>Used to transfer web pages.</td>
    </tr>

    <tr>
        <td>2</td>
        <td>HTTPS</td>
        <td>Hypertext Transfer Protocol Secure</td>
        <td>Provides secure communication on websites.</td>
    </tr>

    <tr>
        <td>3</td>
        <td>FTP</td>
        <td>File Transfer Protocol</td>
        <td>Used to transfer files between computers.</td>
    </tr>

    <tr>
        <td>4</td>
        <td>TCP</td>
        <td>Transmission Control Protocol</td>
        <td>Ensures reliable data transmission.</td>
    </tr>

    <tr>
        <td>5</td>
        <td>UDP</td>
        <td>User Datagram Protocol</td>
        <td>Transfers data quickly without guaranteed delivery.</td>
    </tr>

    <tr>
        <td>6</td>
        <td>IP</td>
        <td>Internet Protocol</td>
        <td>Provides addressing and routing of data.</td>
    </tr>

    <tr>
        <td>7</td>
        <td>SMTP</td>
        <td>Simple Mail Transfer Protocol</td>
        <td>Used to send emails.</td>
    </tr>

    <tr>
        <td>8</td>
        <td>DNS</td>
        <td>Domain Name System</td>
        <td>Converts domain names into IP addresses.</td>
    </tr>

    <tr>
        <td>9</td>
        <td>POP3</td>
        <td>Post Office Protocol Version 3</td>
        <td>Used to receive and download emails.</td>
    </tr>

    <tr>
        <td>10</td>
        <td>SSH</td>
        <td>Secure Shell</td>
        <td>Provides secure remote access to computers.</td>
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
server_address = ('',5000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~


## OUTPUT:
<img width="1051" height="156" alt="8b6cc9e5-e3a6-4b36-8822-c04892da6937" src="https://github.com/user-attachments/assets/4492509c-f796-48fc-bc3c-a40cd844b7b5" />


## RESULT:

<img width="1118" height="851" alt="2dc25463-0791-4b2b-9996-03b1f2be28d4" src="https://github.com/user-attachments/assets/d94dcd42-84c6-41f5-bf39-c5826e7353c3" />

The program for implementing simple webserver is executed successfully.

