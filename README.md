# EX01 Developing a Simple Webserver

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

~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<title>Top Software Industries</title>
<body>
<table border="2" cellspacing="10" cellpadding="6">
<caption>Top 5 Revenue Generating Software Companies</caption>
<tr>
<th>s.no</th>
<th>Company</th>
<th>Revenue</th>
</tr>
<tr>
<th>1</td>
<th>Microsoft</td>
<th>65 Billion</td>
</tr>
<tr>
<th>2</th>
<th>Oracle</th>
<th>29.6 Billion</th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>29.1 Billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.4 Billion</th>
</tr>
<tr>
<th>5</th>
<th>Symantec</th>
<th>5.6 Billion</th>
</tr>
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
~~~

## OUTPUT:
![Screenshot 2024-03-24 211413](https://github.com/Harevasu/simplewebserver/assets/147985044/e54a907d-d6db-4870-aa1e-1bba3b33d456)


![Screenshot 2024-03-24 211435](https://github.com/Harevasu/simplewebserver/assets/147985044/4a7eb51f-9115-4c96-a40c-689225146633)

## RESULT:
The program for implementing simple webserver is executed successfully.
