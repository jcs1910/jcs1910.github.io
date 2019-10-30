---
title: "[QUIC] The Road to faster and safer network protocol"
date: "2019-10-27T16:25:12.199Z"
template: "post"
draft: false
slug: "/posts/The-Road-to-faster-and-safer-network protocol/"
category: "HTTP"
tags:
  - "QUIC"
  - "UDP"
  - "HTTP"
  - "TCP/IP"

description: "The road to QUIC"
---

<figure>
    <img src="/media/nature-photo3.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

This posts illustrates QUIC a new protocol designed by Google. As I dig deeper into details of Internet Protocol (IP), the standard encoding scheme for sending audio and video files. We cannot talk about IP without understanding TCP/IP, which bascailly describes a protocol that will work on any sort of computer for transporting packets of data acroos the Internet. 

With the use of TCP/IP, users can send high-quality audio and video feeds over long distances. In short, time and space limitations are no longer valid. Despite the huge progress over networking technology, hassles such as latency and security have remained. That's why, the road to accelerate HTTP traffic is underway and Google is at the forefront of it. 

<figure>
    <img src="/media/quic.png" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

## Speed (Latency)

There is always a trades-off in computer networking. TCP, developed in the 1970s, converts data into packets and sends them to the Internet. According to the Internet Engineering Task Force (IETF), more than 90% of IP traffic is sent over TCP. TCP is designed to reduce the transmission rates by monitoring the number of packets lost during transmission to capture congestion. On the contrary, with QUIC, a server can start sending data without any round trips when a client talks to a given server to help web pages load faster. According to its performance result, QUIC improves loading times by 8% globally, and up to 13% in regions where latency is higher. 

<figure>
    <img src="/media/quic VS TCP.png" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

I recently read an article about Uber's adoption of QUIC protocol. A giant global tech company, Uber, strives to achieve the real-time performance to increase user experiences. Whether Uber's rider app to success with QUIC remain to be seen.

## Security

Another merit QUIC is different from now venerable TCP is the stated design goal of providing a secure-by-default transport protocol. QUIC accomplishes this by providing security features, like authentication and encryption, that are typically handled by a higher layer protocol (like TLS), from the transport protocol itself.

## The Future of QUIC

QUIC is designed to evolve over time. A client and server can negotiate which version of QUIC to use, and as the IETF QUIC specifications become more stable and members reach clear consensus on key decisions, some have used that version negotiation to keep pace with the current IETF drafts. Future planned versions will also include features such as partial reliability, multipath, and support for non-HTTP applications like WebRTC.

As a backend developer, the evolution of Internet Protocol interests and motivates me to catch more insights into the fundamentals of HTTP reqeusts and responses through QUIC.

### Ref 
- https://cloud.google.com/load-balancing/docs/https/#QUIC
- https://www.fastvue.co/fastvue/blog/googles-quic-protocols-security-and-reporting-implications/

---

> **We are creating wealth every time we write a code**
