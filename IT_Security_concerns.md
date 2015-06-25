django security/sanitization doc : http://www.djangobook.com/en/2.0/chapter20/

## XSS ##

Major concerns are stored data being shown and containing javascript
also any shown data should be escaped
Django can do this by adding "|escape" to the variable/dynamic content to be escaped

see : http://www.djangobook.com/en/2.0/chapter20/

## Sessions ##

to be updated

### URLS ###

relative urls are safe for the W3 :D http://www.w3.org/Addressing/rfc1808.txt