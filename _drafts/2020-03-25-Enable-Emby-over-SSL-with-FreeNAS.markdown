---
layout: post
title: Create a custom jail for OpenVPN in FreeNAS
date:
---

## Scenario  
I run Emby on FreeNAS, inside a jail.  This will go over the process I used to create a **self-signed** SSL certificate to use with Emby.  

## Create self-signed SSL certificate  
I pretty much stuck to the FreeBSD documentation for this.  That can be found [here](https://www.freebsd.org/doc/handbook/openssl.html)  
`openssl genrsa -rand -genkey -out cert.key 2048`  
`openssl req -new -x509 -days 365 -key cert.key -out cert.crt -sha256`  
`openssl pkcs12 -export -in cert.crt -inkey cert.key -out newcert.pfx`  
