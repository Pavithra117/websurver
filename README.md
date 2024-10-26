# EX01 Developing a Simple Webserver
## Date:26.10.24

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!DODTYPE html>
<html>
    <head>
        <title>COMPUTER CONFIGURATION</title>
    </head>
    <body>
        <table border="2" cellspacing="10" cellpading="6">
            <tr>
                <th>S.NO</th>
                <th>SYSTEM CONFIGURATION</th>
                <th>DEVICE</th>
            </tr>
            <TR>
                <th>1</th>
                <th>PROCESSOR</th>
                <th>i5-1235U 1.30GHz</th>
            </TR>
            <TR>
                <th>2</th>
                <th>INSTALLED RAM</th>
                <th>16GB RAM</th>
            </TR>
            <TR>
                <th>3</th>
                <th>SYSTEM TYPE</th>
                <th>64-bit operating system</th>
            </TR>
            <TR>
                <th>4</th>
                <th>OS BUILD</th>
                <th>22631.4317</th>
            </TR>
            <TR>
                <th>5</th>
                <th>VERSION</th>
                <th>23H2</th>
            </TR>
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
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

## OUTPUT:
![alt text](<Screenshot 2024-10-26 105417.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
