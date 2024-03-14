# EX01 Developing a Simple Webserver
## Date:

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
content="""
<html>
<title>Top Software Industries</title>
<body>
<table border="2" cellspacing="10" cellpadding="6">
<caption>Top 5 Revenue Generating Software Companies </caption>
<tr>
<th>s.no</th>
<th>companies</th>
<th>revenue</th>
</tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>65 billion</th>
</tr>
<tr>
<th>2</th>
<th>oracle</th>
<th>29.6 billion</th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>29.1 billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.4 billion</th>
</tr>
<tr>
<th>5</th>
<th>SYMENTEC</th>
<th>6 billion</th>
</tr>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header("content-type", "text/html; charset-utf-8")
        self.end_headers()
        self.wfile.write(content.encode())
server_address=('',8000)
httpd=HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![Screenshot 2024-03-14 135149](https://github.com/Rohanjeyachandiran/simplewebserver/assets/161102491/9482f1d5-fc79-4fd2-a91b-6727e02ee06f)
![Screenshot 2024-03-14 135205](https://github.com/Rohanjeyachandiran/simplewebserver/assets/161102491/7c316563-c768-4052-ac85-7d9d0280eb5e)
![Screenshot 2024-03-14 135011](https://github.com/Rohanjeyachandiran/simplewebserver/assets/161102491/5b1e95a0-b463-45c1-a534-809eb221502a)





## RESULT:
The program for implementing simple webserver is executed successfully.
