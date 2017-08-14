---
title: Security / Tools
tags: [sec, tool]
keywords: security, tools, tool
sidebar: wiki_sidebar
permalink: sec_tools.html
---

## Scanners

[w3af](http://w3af.org/) | Open Source Web Application Security Scanner
[Scanning for OWASP Top 10 Vulnerabilities with Metasploit for the web(w3af)](https://gbhackers.com/scanning-owsap-top-10-vulnerabilities-metasploit-webw3af/) |

## Web Proxy

[BURP Suite](https://portswigger.net/burp) | An integrated platform for performing security testing of web applications. Its various tools work seamlessly together to support the entire testing process, from initial mapping and analysis of an application's attack surface, through to finding and exploiting security vulnerabilities.
[OWASP ZAP](https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project) | One of the world’s most popular free security tools and is actively maintained by hundreds of international volunteers. It can help you automatically find security vulnerabilities in your web applications while you are developing and testing your applications. Its also a great tool for experienced pentesters to use for manual security testing.
[Charles Proxy](https://www.charlesproxy.com/) | HTTP proxy / HTTP monitor / Reverse Proxy that enables a developer to view all of the HTTP and SSL / HTTPS traffic between their machine and the Internet. This includes requests, responses and the HTTP headers (which contain the cookies and caching information).
[Fiddler](http://www.telerik.com/fiddler) | The free web debugging proxy for any browser, system or platform


## Network

[Nmap Cheat Sheet](https://www.stationx.net/nmap-cheat-sheet/) | Network exploration tool and security / port scanner.

## Reversing

### Linux Commands/Tools

* `strings`
* `hexdump -C`
* `readelf -a`
* `file`
* `lsof -i`
* `strace`
* `ltrace`
* `radare2`

### Websites

* [Compiler Explorer](https://godbolt.org/#) is an interactive tool that lets you type code in one window and see the results of its compilation in another window. You can "translate" C code to assembler in **real time**.
* [Reverse engineering for malware analysis cheatsheet](http://pax0r.com/staff/reverse.png)

## SSL
* `openssl s_client -connect www.feistyduck.com:443` -- Connect via SSL/TLS  
(Useful parameters: `-quiet`, `-ign_eof`)  
<sup>Reference: [Debug SSL/TLS](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)</sup>

## Pentesting Suite

[Metasploit](https://www.metasploit.com/) by Rapid7 | The Metasploit Project host the world’s largest public database of quality-assured exploits.


## Dictionaries

[pydictor](http://www.kitploit.com/2017/08/pydictor-powerful-and-useful-hacker.html) | A Powerful and Useful Hacker Dictionary Builder for a Brute-Force Attack
