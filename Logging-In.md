# Logging In

First, You Need to Send A Request To Discord's Servers With A Username And Password

```Request
URL: https://discord.com/api/v10/auth/login
METHOD: POST
BODY: {
    captcha_key: null,
    gift_code_sku_id: null,
    login: "Email@Here.com",
    login_source: null,
    password: "PasswordHere",
    undelete (Is It Undeleting An Account): false
}
```

You Will Recieve This Data On Success:

```Response
{
    captcha_key: ["captcha-required"],
    captcha_service: "hcaptcha",
    captcha_sitekey: "Key For Captcha"
}
```

Then, You Will Have To Go Through A Captcha Verification Process And Complete The Captcha With The Recieved `captcha_key`

Then, Send A Request As So:

```Request
URL: https://discord.com/api/v10/auth/login
METHOD: POST
BODY: {
    captcha_key: "The `captcha_key` You Completed With",
    gift_code_sku_id: null,
    login: "Email@Here.com",
    login_source: null,
    password: "PasswordHere",
    undelete (Is It Undeleting An Account): false
}
```

You Will Recieve This Data On Success:

```Response
{
    mfa (Requires Authenticator App): true | false,
    sms (Has Phone Number): true | false,
    ticket (null if `mfa` is false): null | "MFA Ticket",
    token (null if `mfa` is true): null | "User Token"
}
```

If Your Returned `mfa` Value Is False, You Can Skip This Next Part.

If Your `mfa` Value Is True, You Must Get A Verification Code (6 Digit Number) From The User, Then Send A Request As So:

```Request
URL: https://discord.com/api/v10/auth/mfa/totp
METHOD: POST
BODY: {
    code: "The Verification Code",
    gift_code_sku_id: null,
    login_source: null,
    ticket: "The `mfa` Ticket"
}
```

And You Should Recieve:

```Response
{
    token: "User Token"
}
```

<br />

Now, You've Successfully Logged Into You're User's Account And Have Obtained A User Token.
