# HTB - Web Requests

## HTTP

**HTTP (HyperText Transfer Protocol)** is used for communication between a client and a server.

### Default Ports

| Protocol | Port |
|----------|------|
| HTTP | 80 |
| HTTPS | 443 |

### Flow

```text
Client  --->  Request  --->  Server
Client  <---  Response <---  Server
```

**Key Points**
- Application Layer Protocol
- Stateless Protocol

---

## URL

A URL (Uniform Resource Locator) is the address of a resource on the internet.

### Example

```text
https://www.example.com/login
```

### Components

| Component | Value |
|-----------|--------|
| Protocol | https |
| Domain | www.example.com |
| Path | /login |

---

## cURL

cURL is a command-line tool used to transfer data using URLs.

### Display Content

```bash
curl http://example.com
```

### Download File (Original Name)

```bash
curl -O http://example.com/file.txt
```

### Download File (Custom Name)

```bash
curl -o myfile.txt http://example.com/file.txt
```

## Common Options

| Option | Description |
|---------|-------------|
| `-O` | Save with original filename |
| `-o` | Save with custom filename |
| `-I` | Show HTTP headers |
| `-L` | Follow redirects |

---

## Summary

- HTTP → Port 80
- HTTPS → Port 443
- URL identifies a resource
- cURL interacts with web servers

## HTTPS

HTTPS (HyperText Transfer Protocol Secure) is the secure version of HTTP.

### Why HTTPS?

- Encrypts data between client and server.
- Prevents eavesdropping.
- Protects sensitive information such as passwords and payment details.
- Provides authentication through SSL/TLS certificates.

### HTTPS Flow

```text
Client ---> HTTPS Request ---> Server
Client <--- Encrypted Response <--- Server
```

### SSL/TLS Certificate

- Used to establish a secure connection.
- Verifies the identity of the website.
- Represented by the lock icon in the browser.

### Important Notes

- HTTPS encrypts web traffic.
- DNS requests may still reveal the visited domain if DNS is not encrypted.
- Encrypted DNS or a VPN can improve privacy.

### Key Takeaways

- HTTPS = HTTP + SSL/TLS
- Uses Port 443
- Encrypts communication
- Protects confidentiality and integrity of data
---

## HTTP Request Structure

An HTTP Request contains:

| Field | Description |
|---------|-------------|
| Method | Action to perform (GET, POST, etc.) |
| Path | Resource being requested |
| Version | HTTP version |

### Example

```http
GET /users/login.html HTTP/1.1

### Common Request Headers

| Header | Purpose |
|----------|----------|
| Host | Target website |
| User-Agent | Browser/Client information |
| Cookie | Session information |
| Accept | Accepted content type |

---

## HTTP Response Structure

An HTTP Response contains:

1. Status Line
2. Response Headers
3. Response Body

### Common Response Headers

| Header | Purpose |
|----------|----------|
| Server | Web server information |
| Content-Type | Type of content returned |
| Content-Length | Size of response |
| Set-Cookie | Creates a cookie |

---

## HTTP Status Codes

| Code | Meaning |
|--------|----------|
| 200 | OK |
| 301 | Moved Permanently |
| 302 | Redirect |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

## cURL Verbose Mode

Show full HTTP request and response:

```bash
curl -v http://example.com
```

Useful for:
- Viewing request headers
- Viewing response headers
- Debugging web applications
- Web penetration testing

---

## Browser DevTools

Open DevTools:

```text
F12
```
or

```text
Ctrl + Shift + I
```
### Network Tab

Used to:

- View HTTP requests
- View HTTP responses
- Inspect headers
- Monitor web traffic
- Analyze web applications

### Why Important?

The Network tab is one of the most used tools in web application testing and penetration testing.