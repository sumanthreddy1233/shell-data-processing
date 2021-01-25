# Shell data processing 
## Some interesting powershell commands
### invoke command 
- runs (command on local and remote machine)
### import module 
- ipmo (adds modules to the current session)
### Get-WmiObject
-  gwmi (Gets instances of WMI classes or information about the available classes)
## Interesting things in CURL
### About Curl
curl is a tool to transfer data from or to a server, using one of the supported protocols (DICT, FILE, FTP, FTPS, GOPHER, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, MQTT, POP3, POP3S, RTMP, RTMPS, RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, TELNET and TFTP). The command is designed to work without user interaction.

curl offers a busload of useful tricks like proxy support, user authentication, FTP upload, HTTP post, SSL connections, cookies, file transfer resume, Metalink, and more. As you will see below, the number of features will make your head spin!

curl is powered by libcurl for all transfer-related features. See libcurl(3) for details.
### URL
The URL syntax is protocol-dependent. You'll find a detailed description in RFC 3986.

You can specify multiple URLs or parts of URLs by writing part sets within braces and quoting the URL as in:

  "http://site.{one,two,three}.com"

or you can get sequences of alphanumeric series by using [] as in:

  "ftp://ftp.example.com/file[1-100].txt"

  "ftp://ftp.example.com/file[001-100].txt" (with leading zeros)

  "ftp://ftp.example.com/file[a-z].txt"

Nested sequences are not supported, but you can use several ones next to each other:

  "http://example.com/archive[1996-1999]/vol[1-4]/part{a,b,c}.html"

You can specify any amount of URLs on the command line. They will be fetched in a sequential manner in the specified order. You can specify command line options and URLs mixed and in any order on the command line.

You can specify a step counter for the ranges to get every Nth number or letter:

  "http://example.com/file[1-100:10].txt"

  "http://example.com/file[a-z:2].txt"

When using [] or {} sequences when invoked from a command line prompt, you probably have to put the full URL within double quotes to avoid the shell from interfering with it. This also goes for other characters treated special, like for example '&', '?' and '*'.

Provide the IPv6 zone index in the URL with an escaped percentage sign and the interface name. Like in

  "http://[fe80::3%25eth0]/"

If you specify URL without protocol:// prefix, curl will attempt to guess what protocol you might want. It will then default to HTTP but try other protocols based on often-used host name prefixes. For example, for host names starting with "ftp." curl will assume you want to speak FTP.

curl will do its best to use what you pass to it as a URL. It is not trying to validate it as a syntactically correct URL by any means but is instead very liberal with what it accepts.

curl will attempt to re-use connections for multiple file transfers, so that getting many files from the same server will not do multiple connects / handshakes. This improves speed. Of course this is only done on files specified on a single command line and cannot be used between separate curl invokes.
### Protocols
curl supports numerous protocols, or put in URL terms: schemes. Your particular build may not support them all.

DICT

Lets you lookup words using online dictionaries.

FILE

Read or write local files. curl does not support accessing file:// URL remotely, but when running on Microsoft Windows using the native UNC approach will work.

FTP(S)

curl supports the File Transfer Protocol with a lot of tweaks and levers. With or without using TLS.

GOPHER

Retrieve files.

HTTP(S)

curl supports HTTP with numerous options and variations. It can speak HTTP version 0.9, 1.0, 1.1, 2 and 3 depending on build options and the correct command line options.

IMAP(S)

Using the mail reading protocol, curl can "download" emails for you. With or without using TLS.

LDAP(S)

curl can do directory lookups for you, with or without TLS.

MQTT

curl supports MQTT version 3. Downloading over MQTT equals "subscribe" to a topic while uploading/posting equals "publish" on a topic. MQTT support is experimental and TLS based MQTT is not supported (yet).

POP3(S)

Downloading from a pop3 server means getting a mail. With or without using TLS.

RTMP(S)

The Realtime Messaging Protocol is primarily used to server streaming media and curl can download it.

RTSP

curl supports RTSP 1.0 downloads.

SCP

curl supports SSH version 2 scp transfers.

SFTP

curl supports SFTP (draft 5) done over SSH version 2.

SMB(S)

curl supports SMB version 1 for upload and download.

SMTP(S)

Uploading contents to an SMTP server means sending an email. With or without TLS.

TELNET

Telling curl to fetch a telnet URL starts an interactive session where it sends what it reads on stdin and outputs what the server sends it.

TFTP

curl can do TFTP downloads and uploads.

## Citation
https://www.pdq.com/powershell/
https://curl.se/docs/manpage.html

