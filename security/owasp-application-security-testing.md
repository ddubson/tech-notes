# OWASP Application Security Testing

### OTG-INFO-001 Conduct search engine discovery recon for info leakage

Use a search engine to conduct recon for:

* Network diagrams and configs
* Archived posts, emails by admins
* Log on procedures and username formats
* Usernames, passwords
* Error message content
* Development, UAT, test, and staging versions of website

Direct methods: searching indexes and content from caches.

Indirect methods: gleaning sensitive design and config by searching forums, newsgroups, and tendering websites.

#### Search Operators

Using `site:` operator in search engines can restrict search results to a specific domain.

Use a diversified search engine approach, each engine crawls the web uniquely

Google has a `cache:` search

## OTG-INFO-002 Web server fingerprinting

Knowing type and version of a running web server  allows testers to determine known vulnerabilities and appropriate exploits to use during testing.

Find version and type of a running web server to determine known vulnerabilities and appropriate exploits to use during testing.

Commands:

```
# nc [target] [80|443] 
HEAD / HTTP/1.0
```

#### Specific Server Behavior

###### Field Ordering

Web servers do not always print headers in the same order, the order in which they do might lead to identification of a server by the pen tester.

###### Malformed requests test

Sending malformed requests or requests of non-existent pages to the server

Servers might come back with different default error messages that can signify their type.

###### Automated Testing

automate fingerprinting activities with freely available tools like httprecon or httprint

#### Remediation

Turn off server identifiers on respective server \(Apache, nginx, IIS, etc.\)







