# Passport

A middleware for authentication and authorization with Express

[Passport.js](http://www.passportjs.org/)

Installing providers for Google and Facebook

```
$ npm install passport --save
$ npm install passport-google-oauth --save
$ npm install passport-facebook --save
```

## Google Auth (OAuth2)

[Google Developers Console](https://console.developers.google.com/apis/credentials)
[Begginer's Guide to Google OAuth2 with Passport.js](https://dev.to/phyllis_yym/beginner-s-guide-to-google-oauth-with-passport-js-2gh4)
[OAuth 2.0 Scopes for Google APIs](https://developers.google.com/identity/protocols/oauth2/scopes)

Scopes for authentication:

+ https://www.googleapis.com/auth/userinfo.email
+ https://www.googleapis.com/auth/userinfo.profile

### Scope [ email, profile ]

Google must return a profile info like this one for `aldinei@gmail.com`

```
profile:
  {"id":"115526675957800535012",
  "displayName":"Aldinei Bastos",
  "name":{"familyName":"Bastos","givenName":"Aldinei"},
  "emails":[{"value":"aldinei@gmail.com","verified":true}],
  "photos":[{"value":"https://lh3.googleusercontent.com/a-/AOh14GjMTmiF5aWSocBHBVF56wcT-DtIIYWVN0vzfN4QnA=s96-c"}],
  "provider":"google"}
```