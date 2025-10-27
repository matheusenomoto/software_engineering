# Web Development

**Browser**

**Uniform Resource Locator (URL)**

**Hypertext Transfer Protocol (HTTP)**

<img width="691" height="187" alt="http_request_example" src="https://github.com/user-attachments/assets/d254c61a-49fe-492f-96ef-40058c9004e4" />

**Curl**

```sh
enomoto@ubuntu:~$ curl google.com
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="http://www.google.com/">here</A>.
</BODY></HTML>

enomoto@ubuntu:~$ curl -I google.com
HTTP/1.1 301 Moved Permanently
Location: http://www.google.com/
Content-Type: text/html; charset=UTF-8
Content-Security-Policy-Report-Only: ...
Date: Mon, 14 Jul 2025 23:30:18 GMT
Expires: Wed, 13 Aug 2025 23:30:18 GMT
Cache-Control: public, max-age=2592000
Server: gws
Content-Length: 219
X-XSS-Protection: 0
X-Frame-Options: SAMEORIGIN
```
**e.g.**

https://www.google.com/search?q=cars

* **search**: params
* **q=cars**: query

**Hypertext Markup Language HTML**

For documents designed to be displayed in a web browser. It defines the content and structure of web content.

```sh
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Matheus Enomoto</title>
</head>
<body>
    Hello, World!
</body>
</html>
```
<img width="731" height="439" alt="html_example" src="https://github.com/user-attachments/assets/c3cff8c3-2b36-4081-9061-dfe7f0ee7010" />

**Cascading Style Sheets CSS**

```html
<body style="color: #3ccd4e; display: flex; justify-content: center;">
    Hello, World!
</body>
```

**or**

```html
<style>
    body {
        color: #3ccd4e;
        display: flex;
        justify-content: center;
        }
</style>
```













