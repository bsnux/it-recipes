Django security checklist
------------------------

This is a simple security checklist for Django based on *Two Scoops of Django* book by Daniel Greenfeld and Audrey Roy.

* Turn Off DEBUG Mode in Production
* Keep Your Secret Keys Secret
* Use Secure Cookies
* Use HTTP Strict Transport Security (HSTS)
* Use Django *Allowed Hosts* Validation
* Always Use CSRF Protection With HTTP Forms That Modify Data
* Posting Data via AJAX
* Prevent Against Cross-Site Scripting (XSS) Attacks
* Beware of the *eval()*, *exec()*, and *execfile()* built-ins
* Never unpickle data received from an untrusted or unauthenticated source
* When using PyYAML, only use safe load()
* Validate All User Input With Django Forms
* Handle User-Uploaded Files Carefully
* Don't Use ModelForms.Meta.exclude
* Beware of SQL Injection Attacks
* Change the Default Admin URL
* Use *django-admin-honeypot*
* Only Allow Admin Access via HTTPS
* Limit Admin Access Based on IP
* Use the *allow tags* attribute With Caution
* Secure the Admin Docs
* Monitor Your Sites
* Keep Your Dependencies Up-to-Date
* Put Up a Vulnerability Reporting Page
* Keep Up-to-Date on General Security Practices
