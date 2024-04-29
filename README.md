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
```
from http.server import HTTPServer,BaseHTTPRequestHandler


content='''

<!doctype html>

<html>
 
<head>
 
<title> My Web Server</title>

</head>

<body>
 
<h1>Top Five Revenue from Companies</h1>

<table border=2>
 
<tr>
 
<th> Company Name </th>

<th> Revenue </th>

<th> Financial Year </th>

</tr>


<tr>
 
<td> Microsoft </td>

<td> 86$ </td>

<td> 2014 </td>

</tr>


<tr>
 
<td> Oracle </td>

<td> 37$ </td>

<td> 2013 </td>

</tr>


<tr>
 
<td> SAP </td>

<td> 20$ </td>

<td> 2013 </td>

</tr>


<tr>
 
<td> VMware </td>

<td> 5.2$ </td>

<td> 2013 </td>

</tr>


<tr>
 
<td> CA Technologies </td>

<td> 4.7$ </td>

<td> 2013 </td>

</tr>


</body>

</html>


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
 ![Screenshot 2024-03-23 012215](https://github.com/RITHISHlearn/simplewebserver/assets/145446645/505ef907-fff1-4060-a4e9-6d249ff6d75a)
![Screenshot 2024-03-23 012230](https://github.com/RITHISHlearn/simplewebserver/assets/145446645/486bb6b9-4d67-47bb-b8f6-e198725f018a)


## RESULT:
The program for implementing simple webserver is executed successfully.
