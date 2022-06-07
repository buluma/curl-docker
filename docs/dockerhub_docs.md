# Supported tags and respective Dockerfile links

* [7.83.1](https://github.com/buluma/curl-docker/blob/master/alpine/latest/Dockerfile)

# Quick reference
* Where to get help: [website](https://curl.haxx.se/), [mailing lists](https://curl.haxx.se/mail/), [Everything Curl](https://curl.haxx.se/book.html)
* Where to file issues: https://github.com/curl/curl-docker/issues
* Maintained by: ShadowNet team
* Supported architectures: amd64, arm64
* github repo: [buluma/curl-docker](https://github.com/buluma/curl-docker)

# What is Curl ?
[curl](https://curl.haxx.se/) is a command line tool and library  for transferring data with URLs.

[curl](https://curl.haxx.se/)  is used in command lines or scripts to transfer data. It is also used in cars, television sets, routers, printers, audio equipment, mobile phones, tablets, settop boxes, media players and is the internet transfer backbone for thousands of software applications affecting billions of humans daily.

Supports the following protocols (so far!):.

DICT, FILE, FTP, FTPS, Gopher, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, POP3, POP3S, RTMP, RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, Telnet and TFTP. curl supports SSL certificates, HTTP POST, HTTP PUT, FTP uploading, HTTP form based upload, proxies, HTTP/2, cookies, user+password authentication (Basic, Plain, Digest, CRAM-MD5, NTLM, Negotiate and Kerberos), file transfer resume, proxy tunneling and more.

# How to use this image

### get docker image

```
> docker pull buluma/curl:... insert tag ...
```

### run docker image
```
> docker run --rm -it buluma/curl:... insert tag ... --version
```
Here is a more specific example
```
> docker run --rm -it buluma/curl:7.83.1 -v https://curl.haxx.se
```
