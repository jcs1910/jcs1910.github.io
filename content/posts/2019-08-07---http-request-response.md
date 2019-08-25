---
title: "[HTTP] Web Communication through Request and Response"
date: "2019-08-08T13:21:15.199Z"
template: "post"
draft: false
slug: "/posts/http-request-response/"
category: "HTTP"
tags:
  - "HTTP"
  - "Request"
  - "Response"
  - "stateless"
  - "HTTPS"
description: "Client sends HTTP request to server and server sends HTTP response"
---

<figure>
    <img src="/media/20190808-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

## 1) Role: `Communication between web servers & clients`

## 2) Two message types: `HTTP Requests / Responses`

- Client sends HTTP request to server and server sends HTTP response

Loading pages, form submit, Ajax calls

## 3) HTTP is stateless. What does that mean?

- Every request is completely independent (each request is a single transaction).
- Programming, Local Storage, Cookies, Sessions are used to create enhanced user experiences.

## 4) What is HTTPS?

**1) HTTPS (Hyper Text Transfer Protocol Secure)**

**2) Data sent is encrypted**

**3) SSL (HTTPS protocol is running on SSL protocol, just the way web is working on the Internet. Advantages of SSL and SSL digital certificate are:**

- Deter hackers from eavesdropping communication content
- Ensure that the site client is accessing is secure
- Prevent distortion of communication content

**4) Install certificate on web host**

## 5) HTTP Requests and Responses are composed of

> 1. A start-line describing the requests to be implemented, or its **status** of whether **successful or a failure**. This start-line is always **a single line.**

> 2. An optional set of **HTTP headers** specifying the request, or describing the body included in the message.

> 3. **A blank line** indicating all meta-information for the request have been sent.

> 4.  An optional body containing data associated with the request (like content of an HTML form), or the document associated with a response. The presence of the body and its size is specified by the start-line and HTTP headers.

[](https://www.notion.so/e4dae99ce7334ea791ea560ec434298e#cb2698a5537b4c54adbab717572a2d85)

## 6) The start line of HTTP request is composed of three elements.

###6.1) An HTTP method (`GET, PUT, POST, DELETE`). `GET` and `POST` are widely used.

- **GET:** Retrieve data from the server
- **POST:** Submit data to the server
- **PUT:** Update data already on the server
- **DELETE:** Deletes data from the server

###6.2) Request Target:

In order to understand request target, you should be familiar with `Endpoints` and `API.` People including myself are even more confused about complicated explanations. I'm going to add links about Endpoints and API, very simple and to the point.

- [https://stackoverflow.com/questions/2122604/what-is-an-endpoint#47573997](https://stackoverflow.com/questions/2122604/what-is-an-endpoint#47573997)
- [https://smartbear.com/learn/performance-monitoring/api-endpoints/](https://smartbear.com/learn/performance-monitoring/api-endpoints/)

###6.3) HTTP Version:

- HTTP/1.1

## 7) HTTP General Headers:

- **Request URL**: url reqeust

- **Request Method**: get request and post request

- **Status Code**: 200

- **Remote Address**: IP of remote control

## 8) HTTP General Response:

- **Server:** Most of time, it is hidden to prevent hackers from knowing what types of server the website is using.

- **Set-Cookie:**Set-Cookie is used for servers to send a small piece of data called cookies from client to server

- **Content-Type:** text/css, te xt/html, image/png, application/json

- **Content-Length:** 8bit bite

## 9) Request:

- **Cookies:** Temporary internet files

- **Authorization:** HTTP is stateless, so you need some type of token within the Header for verification

- **User-Agent:** Mozilla or Chrome

## 10) HTTP Status Code

### 1xx: informational

Request received / receiving

### 2xx: Success

Successfully Received, understood and accepted

### 3xx: Redirect

Further action must be taken / redirect

### 4xx: Client Error

Request does not have what it needs

### 5xx: Server Error

Server failed to fulfill an apparent valid request

## 11) Widely known status code

- 200 - OK

- 201 - OK created

- 301 - Moved to new URL

- 304 - Not modified (Cached version)

- 400 - Bad request

- 401 - Unauthorized (missing tokens)

- 404 - Not found

- 500 - Internal server error

---

> **We are creating wealth every time we write a code**
