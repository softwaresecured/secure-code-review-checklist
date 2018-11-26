# secure-code-review-checklist
A starter secure code review checklist

- Available in [Xlsx](Secure_Code_Checklist.xlsx) for offline testing

## Table of Contents

* [Information Gathering](#Information)
* [Configuration](#Configuration)
* [Secure Transmission](#Transmission)
* [Authentication](#Authentication)
* [Session Management](#Session)
* [Authorization](#Authorization)
* [Data Validation](#Validation)
* [Application Output](#Output)
* [Cryptography](#Cryptography)
* [Log Management](#Log)

------
### <a name="Information">Information Gathering</a>
- [ ] Get a copy of the code
- [ ] Manually explore the file structure of the code
- [ ] Look for any missing pieces of code
- [ ] Check for frameworks / libraries / dependencies
- [ ] Check for application routes and their inputs

### <a name="Configuration">Configuration</a>
- [ ] Sensitive data is not hard-coded in configuration files
- [ ] Develop and test code are properly segregated from production
- [ ] Dependencies are up to date

### <a name="Transmission">Secure Transmission</a>
- [ ] Sensitive data is only transmitted over an SSL connection
- [ ] Site is partitioned into private and public URLs
- [ ] Sensitive data has been secured in memory, storage and transit
- [ ] Sensitive data doesn’t leak to non private channels


### <a name="Authentication">Authentication</a>
- [ ] Test for user enumeration
- [ ] Passwords are encrypted using a framework / library
- [ ] Users are unable to login over GET, only POST
- [ ] User credentials are encrypted using framework/library 
- [ ] Strong password policy in effect

### <a name="Session">Session Management</a>
- [ ] Establish how session management is handled in the application
- [ ] Session cookies are encrypted and have a length of at least 128 bits and are complex
- [ ] Session cookies are not persistent
- [ ] Session cookies use cookie attributes httponly, secure, samesite
- [ ] Session tokens are not passed in URLs
- [ ] Session Cookies expire in a reasonable amount of time
- [ ] Logout will invalidate the session

### <a name="Authorization">Authorization</a>
- [ ] Sensitive transactions require re authentication
- [ ] Authentication and Authorization checks are done on each private request
- [ ] Authorization checks are granular, per page / directory / action
- [ ] Authorization checks are appropriate for each HTTP Verb the application supports


### <a name="Validation">Data Validation</a>
- [ ] All user input is validated for proper type, length, format and range
- [ ] Validation on user input is done server side
- [ ] Uploaded files are validated for content type, size, file type and filename
- [ ] Special characters are sanitized before being used in external systems, like databases
- [ ] Does invalid input trigger handled exceptions

### <a name="Output">Application Output</a>
- [ ] All page output is properly encoded
- [ ] All header output is URL encoded
- [ ] Cache headers are properly set on sensitive data
- [ ] Security headers are properly set on the application
- [ ] Sensitive Application information is not revealed to the user
- [ ] Error messages don’t reveal sensitive information
- [ ] Error messages aren't user controllable

### <a name="Cryptography">Cryptography</a>
- [ ] User passwords are encrypted using a stretching algorithm and uniquely salted
- [ ] Block ciphers operate in CBC and IV values are not reused
- [ ] Salts are unique per user, have over 64 bits of secure random data
- [ ] Check for known bad ciphers (RC4), cryptographic hash functions (MD5) and insecure random number generation

### <a name="Log">Log Management</a>
- [ ] All sensitive user actions are logged with the following: Where, What, When, Who, How answered
- [ ] All sensitive system actions are logged with the following: Where, What, When, Who, How answered
- [ ] Sensitive info is not logged
- [ ] User input is sanitized and validated before being placed in application logs


#### Sources:

- Modelled after: [OWASP-Web-Checklist](https://github.com/0xRadi/OWASP-Web-Checklist)
- [Secure Code Review Checklist]()https://arch.simplicable.com/arch/new/secure-code-review-checklist)
- [Internal Software Secured Checklist](Private)
- [Code Review Checklist – To Perform Effective Code Reviews](https://www.evoketechnologies.com/blog/code-review-checklist-perform-effective-code-reviews/)
- [Java Code Review Checklist](https://dzone.com/articles/java-code-review-checklist)
- [Software Integrity](https://www.synopsys.com/blogs/software-security/code-review-checklist/)
- [Security Audit Checklist: Code Perspective](https://courses.cs.washington.edu/courses/cse403/10wi/lectures/security_audit_checklist.pdf)
- [Stop More Bugs with out Code Review Checklist](https://jesseheines.com/~heines/91.462/Resources/CodeReviewChecklists/StopMoreBugsWithOurCodeReviewChecklist_FogCreekBlog_2015-03-23.pdf)

