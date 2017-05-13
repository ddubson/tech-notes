# Cross Site Scripting \(XSS\)

Cross Site Scripting \(XSS\) is an attack that allows an attacker to execute malicious JS in another user's browser.

Attacker does not target a specific victim, but attempts to catch victims by injecting code into a webpage that will execute when someone navigates to the said page.

## Dangers of XSS

Malicious JS can cause havoc in many different ways:

* User's sensitive information can be gathered
* DOM can be manipulated to be misleading, unusable, or used in concert with another attack to steal information
* AJAX calls can be triggered to external malicious sites

Concrete Dangers:

* Cookie Theft - steal user's cookie and send over to malicious server
* Keylogging - track keyboard events and record gestures
* Phishing - replace an already existing form with a malicious information stealing form

## Example

A simple server side script used to display comments on a web page

```
print "<html>"
print "Latest comment:"
print database.latestComment
print "</html>"
```

The comment that is rendered has the XSS payload:

```
<html>
Latest comment:
<script>...</script>
</html>
```

# Resources

[https://excess-xss.com/](https://excess-xss.com/)

[https://www.owasp.org/index.php/Cross-site\_Scripting\_\(XSS\)](https://www.owasp.org/index.php/Cross-site_Scripting_%28XSS%29)





