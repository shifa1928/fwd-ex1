# EX01 Developing a Simple Webserver
## Date:03-11-26
## REG NO: 26003336

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
content = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>TCP/IP Protocol Suite</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 40px; background: #f4f6f8; }
        h1 { color: #2c3e50; }
        .layer { background: #fff; padding: 15px; margin-bottom: 15px; border-radius: 5px; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }
        .layer h3 { margin-top: 0; color: #34495e; }
        ul { margin: 5px 0; padding-left: 20px; }
    </style>
</head>
<body>
    <h1>TCP/IP Protocol Suite</h1>
    
    <div class="layer">
        <h3>1. Application Layer (Process/Data)</h3>
        <p>Handles high-level protocols, user authentication, and data formatting.</p>
        <ul>
            <li><strong>HTTP / HTTPS:</strong> Hypertext Transfer Protocol (Secure)</li>
            <li><strong>FTP:</strong> File Transfer Protocol</li>
            <li><strong>SMTP / POP3 / IMAP:</strong> Email services</li>
            <li><strong>DNS:</strong> Domain Name System</li>
            <li><strong>DHCP:</strong> Dynamic Host Configuration Protocol</li>
        </ul>
    </div>

    <div class="layer">
        <h3>2. Transport Layer (Host-to-Host)</h3>
        <p>Manages end-to-end communication, reliability, and flow control.</p>
        <ul>
            <li><strong>TCP:</strong> Transmission Control Protocol (Reliable, connection-oriented)</li>
            <li><strong>UDP:</strong> User Datagram Protocol (Fast, connectionless)</li>
        </ul>
    </div>

    <div class="layer">
        <h3>3. Internet Layer (Network)</h3>
        <p>Handles logical addressing, packet routing, and path determination.</p>
        <ul>
            <li><strong>IP (IPv4 / IPv6):</strong> Internet Protocol</li>
            <li><strong>ICMP:</strong> Internet Control Message Protocol (e.g., ping)</li>
            <li><strong>ARP:</strong> Address Resolution Protocol (Maps IP to MAC)</li>
        </ul>
    </div>

    <div class="layer">
        <h3>4. Network Interface Layer (Link / Physical)</h3>
        <p>Deals with physical transmission and local network hardware frames.</p>
        <ul>
            <li><strong>Ethernet</strong></li>
            <li><strong>Wi-Fi (IEEE 802.11)</strong></li>
            <li><strong>PPP:</strong> Point-to-Point Protocol</li>
        </ul>
    </div>
</body>
</html>"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',890)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

~~~

## OUTPUT:

![alt text](<Screenshot 2026-11-03 141308.png>)

![alt text](<Screenshot 2026-11-03 141326.png>)
![alt text](<Screenshot 2026-11-03 141336.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

