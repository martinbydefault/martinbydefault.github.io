---
title: Security / Web
tags: [sec, web]
keywords: security, web, sec
sidebar: wiki_sidebar
permalink: sec_web.html
---

## CORS - **C**ross **O**rigin **R**esource **S**haring
Introduction to **CORS**:
* [Cross-domain Ajax with Cross-Origin Resource Sharing](https://www.nczonline.net/blog/2010/05/25/cross-domain-ajax-with-cross-origin-resource-sharing/)
* [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS) by MDN  
[Same Origin Policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy) by MDN
* [Bypassing Same Origin Policy](http://qnimate.com/same-origin-policy-in-nutshell/)

## CSRF - **C**ross **S**ite **R**equest **F**orgery

[**CSRF** Demystified](http://www.gnucitizen.org/blog/csrf-demystified/) | I will try to provide a basic explanation about the attack pattern itself, come up with several real word examples and finally summarize a list of things developers can do to protect their sites against CSRF attacks.
[All You need To KnowA bout Cross Site Request Forgery (CSRF)](https://www.darknet.org.uk/2017/07/all-you-need-to-know-about-cross-site-request-forgery-csrf/) | A compilation of links by darknet.org.uk
[Anatomy of a Cross-site Request Forgery Attack](haacked.com/archive/2009/04/02/anatomy-of-csrf-attack.aspx/) | Various code examples about CSRF
[CSRF Mitigation for AJAX Requests](https://markitzeroday.com/x-requested-with/cors/2017/06/29/csrf-mitigation-for-ajax-requests.html) | Ways to mitagate CSRF AJAX Requests

### Others

**Submit a HTML form without redirection**  
<sup>Reference: [Stackoverflow - How to submit html form without redirection?](https://stackoverflow.com/questions/25983603/how-to-submit-html-form-without-redirection)</sup>

```html
<iframe width="0" height="0" border="0" name="dummyframe" id="dummyframe"></iframe>

<form action="submitscript.php" target="dummyframe">
    <!-- form body here -->
</form>
```

## XSS - Cross Site Scripting

[Understanding XSS Auditor](https://www.virtuesecurity.com/blog/understanding-xss-auditor/) |  We see a lot of confusion regarding the X-XSS-Protection header and thought it might be worthwhile to go over exactly what this header is and what it isn’t.
[X-XSS-Protection header](https://www.owasp.org/index.php/OWASP_Secure_Headers_Project#xxxsp) | Explanation by OWASP.
[HTML5 Security Cheatsheet](http://html5sec.org/) | A collection of HTML5 related XSS attack vectors, a set of useful files for XSS testing and a set of formerly hidden features useful for XSS testing.

## SQL Injection

[ MySQL injection tutorial](https://www.hellboundhackers.org/articles/read-article.php?article_id=862) by sam207 | In this tutorial, I will demonstrate the infamous MySQL injection in newbie perspective so that all the newbies become able to become successful SQL injector.

## OWASP Top 10


## Special/New Attacks

[Web Cache Deception Attack](https://omergil.blogspot.com/2017/02/web-cache-deception-attack.html) |  Web cache deception is a new web attack vector that puts various technologies and frameworks at risk.

# HTTP

[Insecure HTTP headers](https://veggiespam.com/http-header-removal/) | This page is a collection of instructions to remove unnecessary server headers which may be reported as part of a Penetration Test performed by a security engineer or reported via automated tools.

# HPKP & HSTS

[HPKP y HSTS: Global analysis and implementation](https://www.elevenpaths.com/wp-content/uploads/2017/07/HPKP_HSTS_EN.pdf) by ElevenPaths |
[Is HTTP Public Key Pinning Dead?](https://blog.qualys.com/ssllabs/2016/09/06/is-http-public-key-pinning-dead) | Comments about current state of HPKP.
