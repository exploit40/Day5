# SAML BUGS

* SAML Authorization Bypass

### SAML Authorization Bypass

- [x] let victim mail = john@gmail.com
- [x] make a new mail as attacker = not-a-john@gmail.com
- [x] open login page and whicle intercept on fill your detail not victim in login form
- [x] constantly look for saml request using extension in burpsuite.
- [x] now in saml request you will see email as not-a-john@gmail.com.
- [x] replace it with not-a-\<!-- this is comment -->john@gmail.com and forward it
- [x] if saml is not verifying signature due to comment it will give access to the victim account which is john@gmail.com
