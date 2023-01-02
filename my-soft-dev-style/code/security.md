1.  Practice regular table tops and red team exercises. Treat random bug bounty or vulnerability disclosures as full blown practice incidents. Practice scenarios where you are not in control, you are not omniscient, the right log doesn’t exist and talent can’t understand an issue. Fight from the ground every now and then with your team.
2.  One simple rule allows web developers to prevent cross-site scripting attacks: Don’t trust any input that comes from users. 
3.  Add security log level to log4j for my little rest api project.
4.  Cryptography is not solution to all security problems.
5.  Cryptography is reliable only, if implemented and used properly! 
6.  Hash(password+salt) makes password longer,but not more secure.
7.  It protects by using a rainbow table for reversing hashes by brute force.
8.  It protects other "the same" passwords from being found. If user A and B using the same password,for example "password" ,then salt+password makes them looks different , because every salt for every user is different.
9.  Never reuse a salt. If user changed password,create new salt.
10. Key stretching. you will need extra computational resources to process large volumes of authentication requests, and that key stretching may make it easier to run a Denial of Service (DoS) attack on your website
11. The denial of service threat can be eliminated by making the user solve a CAPTCHA every time they log in.
12. Add a secret key to the hash so that only someone who knows the key can use the hash validate a password.
13. Browser-side security: Mitigate the risk of XSS.
14. Delivery of quick security fixes through auto-update.
15. How to select easy to remember but hard to guess password? This comics strip gives best solution: http://xkcd.com/936/
16. What to do , if struggle with remember password? Use KeePass  (http://keepass.info) a handy tool to keep your password.
17. Never store credentials as code/config in GitHub. 
18. Block sensitive data being pushed to GitHub by git-secrets or its likes as a git pre-commit hook.
19. Use ENV variables for secrets in CI/CD and secret managers like Vault in production.
20. If sensitive data made to a repo after all:
    -   Invalidate tokens and passwords.
    -   Remove the info and clear the GitHub history
21. Tightly control access
    -   Require Two-factor authentication for all your GitHub accounts.
    -   Diligently revoke access from users who are no longer working with you.
    -   Manage team access to data. Give contributors only access to what they need to do their work.
22. Add a SECURITY.md file
    -   You should include a SECURITY.md file that highlights security related information for your project. This should contain:
        -   Disclosure policy. Define the procedure for what a reporter who finds a security issue needs to do in order to fully disclose the problem safely, including who to contact and how. Consider HackerOne’s community edition or simply a ‘security@’ email.
    -   Security Update policy. Define how you intend to update users about new security vulnerabilities as they are found.
    -   Security related configuration. Settings users should consider that would impact the security posture of deploying this project, such as HTTPS, authorisation and many others.
    -   Known security gaps & future enhancements. Security improvements you haven’t gotten to yet. Inform users those security controls aren’t in place, and perhaps suggest they contribute an implementation! For some great reference examples of SECURITY.md files, look at Apache Storm and TensorFlow.
23. Add Security testing to PRs
24. Spring Boot Security
    -   Use HTTPS in Production
    -   Test Your Dependencies. Ensure your application does not use dependencies with known vulnerabilities.
    -   Spring Security enables CSRF support by default. If you use a JavaScript framework, configure the CookieCsrfTokenRepository so cookies are not HTTP-only
0.  Protect the integrity of logs. Forward them to another system so they can be archived and can't be modified.
0.  Protect your keys! Never store symmetric keys, asymmetric private keys, or passwords unencrypted on disk, in databases, or in source code repositories.
0.  Authentication and authorisation. Deny by default, permit when necessary.
0.  Always Escape, encode, and parameterize user input so it can't be interpreted maliciously. 
