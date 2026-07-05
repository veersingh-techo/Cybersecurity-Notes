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
```
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

# HTTP Requests - Practical (HTB)

## HTTP Method
- Use `curl -v` to view request and response headers.
- The first line of the request contains the HTTP method.

### Command
```bash
curl -v http://<IP>:<PORT>
```

### Example
```http
> GET / HTTP/1.1
```

**HTTP Method:** `GET`

---

## Server Version
- Check the `Server` response header to identify the web server and its version.

### Example
```http
< Server: Apache/2.4.41 (Ubuntu)
```

- **Web Server:** Apache
- **Version:** `2.4.41`

---
# HTTP Headers (HTB)

## What are HTTP Headers?
- Metadata sent between **Client** and **Server**.
- Used in both **HTTP Requests** and **HTTP Responses**.
- Format:
```http
Header-Name: Value
```

---

## Types of HTTP Headers
1. **General Headers** – Used in both requests and responses.
2. **Entity Headers** – Describe the message body/content.
3. **Request Headers** – Sent by the client.
4. **Response Headers** – Sent by the server.
5. **Security Headers** – Improve web security.

---

# cURL Header Options

## `-v` (Verbose)
Shows:
- Request Headers
- Response Headers
- Response Body

```bash
curl -v http://example.com
```

---

## `-I`
Sends a **HEAD** request and displays **only response headers**.

```bash
curl -I http://example.com
```

---

## `-i`
Displays:
- Response Headers
- Response Body

```bash
curl -i http://example.com
```

---

## `-A`
Sets a custom **User-Agent**.

```bash
curl -A "Mozilla/5.0" http://example.com
```

Combine with `-v` or `-I` to verify the changed User-Agent.

---

## Quick Revision
- `-v` → Request + Response Headers + Body
- `-I` → HEAD request + Response Headers only
- `-i` → Response Headers + Body
- `-A` → Change User-Agent
- **Network Tab** → Analyze requests and responses

# HTTP Methods & Status Codes (HTB)

## HTTP Methods

### GET
- Retrieve data/resource.
- Data sent in URL (Query Parameters).
- Example:
```http
GET /page?id=1
```

### POST
- Send data to the server.
- Used for forms, login, file uploads.
- Data is sent in the **request body**.

### HEAD
- Same as GET, but **returns headers only** (no body).
- Used to check resource info.

### PUT
- Create or replace a resource.
- Common in REST APIs.

### DELETE
- Delete a resource.
- Common in REST APIs.

### OPTIONS
- Shows supported HTTP methods for a resource.

### PATCH
- Partially update a resource.

> **Most Important:** `GET`, `POST`, `PUT`, `DELETE`

---

# HTTP Status Codes

## Classes
- **1xx** → Informational
- **2xx** → Success
- **3xx** → Redirection
- **4xx** → Client Error
- **5xx** → Server Error

---

## HTB / Pentesting Tips
- **200** → Resource exists.
- **302** → Login/redirect detected.
- **403** → Resource exists but access denied.
- **404** → Resource doesn't exist.
- **500** → Server-side issue; may reveal vulnerabilities.

# GET Request

## Key Concepts
- Default HTTP method used to retrieve data.
- Parameters are sent in the URL.
- Example:
  ```
  /search.php?search=flag
  ```

## HTTP Basic Authentication
- Uses username & password.
- Credentials are sent in the `Authorization` header.
- Authenticate with:
  ```bash
  curl -u username:password http://IP:PORT
  ```

## Authorization Header
- Contains authentication information.
- View request & headers:
  ```bash
  curl -v -u username:password http://IP:PORT
  ```

## GET Parameters
- Syntax:
  ```
  ?key=value
  ```
- Example:
  ```bash
  curl -u admin:admin "http://IP:PORT/search.php?search=flag"
  ```

## Practical Workflow
1. Open **DevTools → Network**.
2. Perform the action (Search/Login).
3. Identify the request URL/API endpoint.
4. If needed, inspect `script.js` to find hidden endpoints.
5. Reproduce the request using `curl`.

## Cybersecurity Relevance
- Analyze browser-server communication.
- Discover hidden API endpoints.
- Test HTTP requests manually.
- Understand authentication headers.
- Foundation for Web Pentesting & API Testing.
---
# POST Requests

## What is POST?
- Used to send data in the **HTTP Request Body** instead of the URL.
- Commonly used for:
  - Login forms
  - File uploads
  - Form submissions
  - JSON/API requests

## Why POST instead of GET?
- Data is not visible in the URL.
- Can send large amounts of data.
- Supports binary/file uploads.
- Less URL encoding required.

## Basic cURL POST Request
```bash
curl -X POST -d "username=admin&password=admin" http://<SERVER_IP>:<PORT>/
```

- `-X POST` → Use POST method.
- `-d` → Send request body.

## Cookies
- After successful login, server sends a **Set-Cookie** header.
- Browser stores it to keep the user authenticated.

Example:
```
Set-Cookie: PHPSESSID=<session_id>
```

Use the cookie:
```bash
curl -b "PHPSESSID=<session_id>" http://<SERVER_IP>:<PORT>/
```

or

```bash
curl -H "Cookie: PHPSESSID=<session_id>" http://<SERVER_IP>:<PORT>/
```

## JSON POST Requests

JSON requests require:

```http
Content-Type: application/json
```

Example JSON body:

```json
{
  "search": "london"
}
```

Example:

```bash
curl -X POST \
-H "Content-Type: application/json" \
-d '{"search":"london"}' \
http://<SERVER_IP>/search.php
```

## Browser DevTools
Useful tabs:
- **Network** → Capture requests.
- **Request** → View headers & body.
- **Storage/Application** → View cookies.

## Cybersecurity Relevance
- Essential for Web Application Pentesting.
- Helps test login forms and authenticated endpoints.
- Used while interacting with APIs.
- Required for tools like Burp Suite, cURL, and Postman.
- Important for Web Security assessments and Bug Bounty.
---
# CRUD API

## What is an API?
- API (Application Programming Interface) allows applications to communicate with a server/database.
- APIs use HTTP methods to perform operations on resources.
- Example Endpoint:
```
http://<SERVER_IP>:<PORT>/api.php/city/london
```

---

# CRUD Operations

| Operation | HTTP Method | Purpose |
|-----------|------------|---------|
| Create | POST | Add new data |
| Read | GET | Retrieve data |
| Update | PUT | Modify existing data |
| Delete | DELETE | Remove data |

---

# 1. Read (GET)

Retrieve an existing resource.

```bash
curl http://<SERVER_IP>:<PORT>/api.php/city/london
```

Pretty JSON output:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/london | jq
```

### Commands
- `-s` → Silent mode (hide cURL progress).
- `jq` → Format JSON output for readability.

---

# 2. Create (POST)

Create a new resource.

```bash
curl -X POST \
-H "Content-Type: application/json" \
-d '{"city_name":"New_HTB_City","country_name":"HTB"}' \
http://<SERVER_IP>:<PORT>/api.php/city
```

### Commands
- `-X POST` → Create data.
- `-H` → Add request header.
- `-d` → Send JSON request body.

---

# 3. Update (PUT)

Modify an existing resource.

```bash
curl -X PUT \
-H "Content-Type: application/json" \
-d '{"city_name":"New_HTB_City","country_name":"HTB"}' \
http://<SERVER_IP>:<PORT>/api.php/city/london
```

### Commands
- `-X PUT` → Update existing data.
- Resource name (`london`) is specified in the URL.

> **PATCH vs PUT**
- **PUT** → Replace the entire resource.
- **PATCH** → Update only selected fields.

---

# 4. Delete (DELETE)

Delete a resource.

```bash
curl -X DELETE \
http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City
```

Verify deletion:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | jq
```

If deleted successfully:

```json
[]
```

---

# Important cURL Flags

| Flag | Purpose |
|------|---------|
| `-X` | Specify HTTP method |
| `-H` | Add request headers |
| `-d` | Send request body |
| `-s` | Silent mode |
| `jq` | Pretty-print JSON |

---

# Cybersecurity Relevance

- Test REST APIs.
- Interact with API endpoints.
- Understand CRUD operations.
- Practice API enumeration.
- Foundation for Burp Suite, Postman, PortSwigger, Bug Bounty, and API Pentesting.

---