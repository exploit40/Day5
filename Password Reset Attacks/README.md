# cookie swap account takeover

* let victim mail = victim@mail.com
* let attacker mail = attacker@mail.com

### steps required to test this vulnerability

- [x] as a attacker login to your account of attacker@mail.com
- [ ] logout it and request for forget password
- [ ] give your security question and it will redirect you to the password reset page do nothing just leave this as it is here for future steps
- [ ] open private tab and request password reset for target mail address which is victim@mail.com while intercept on.
- [ ] copy the cookies.
- [ ] now move to the attcker mail steps where we leave it as it is
- [ ] there now type the new password and before hit enter do intercept on and then hit enter.
- [ ] replace the cookies with victim cookies which you have cpied before and forward it.
- [ ] now login to victim account with new password and see if you were able to takeover victim account.

### MY mind

``` markdown
> Here case was give sequrity question. now what about site where without security question we get verification link in email. no worry if session id is there we can  check this issue their also.

for example get password reset link as attacker and open it and leave it. no in new private tab request password reset link of victim mail and check if any session id or cookie is generated.

now wbere you pause attacker reset link steps. there give new pass and do intercept on and hit enter and in burpsuite replace session id or cookies from attacker to victim and forward it and check login to victim account by using attacker new password.
