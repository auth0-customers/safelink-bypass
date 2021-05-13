# Safelink Bypass Endpoint for Passwordless Login

The purpose of this sample is to demonstrate how to create a simple endpoint to ensure that passwordless magic links still work even if the user is using an email plugin like SafeLink that reviews links before allowing the user to click on them.

** DISCLAIMER ** This example is for example purposes only, this is not production ready tested code and should only be used to learn how the functionality can work.

## Running the Sample

If you don't yet have an Auth0 account, [sign up](https://auth0.com/signup) for free.

## Setup your Auth0 Tenant

* Create a passwordless connection, set the email template to the PasswordlessEmailTemplate.liquid file included in this repo. NOTE: If you search for "link" in the file you will see the changes that were done. It basically sends you to the new endpoint created by this sample and passes the verify_email link as a query parameter. 
* Update your universal login page to match the contents of the file UniversalLoginPage.html. NOTE: The change in the html for this is to use the passwordless template and force it to only email passwordless and to use magic link
* Setup a custom email provider. You can use mailtrap.io if you don't have one
* Create a regular web app that has email passwordless enabled

## Local Setup
Install the dependencies with npm:

```bash
npm install
```

Rename `.env.example` to `.env` and replace the following values:

- `CLIENT_ID` - your Auth0 application client id
- `ISSUER_BASE_URL` - absolute URL to your Auth0 application domain (ie: `https://accountName.auth0.com`)
- `APP_SESSION_SECRET` - a randomly rengerated string. You can generate one on the command line with the following `openssl rand -hex 32`

```bash
mv .env.example .env
```

Run the app:

```bash
npm start
```

The app will be served at `localhost:3000`. Open this page in a browser and click login. Enter your email. A link to login will have been sent to your email. If using mailtrap.io it will be in your mailtrap inbox.

## Vulnerability Reporting

Please do not report security vulnerabilities on the public GitHub issue tracker. The [Responsible Disclosure Program](https://auth0.com/whitehat) details the procedure for disclosing security issues.

## What is Auth0?

Auth0 helps you to easily:

- implement authentication with multiple identity providers, including social (e.g., Google, Facebook, Microsoft, LinkedIn, GitHub, Twitter, etc), or enterprise (e.g., Windows Azure AD, Google Apps, Active Directory, ADFS, SAML, etc.)
- log in users with username/password databases, passwordless, or multi-factor authentication
- link multiple user accounts together
- generate signed JSON Web Tokens to authorize your API calls and flow the user identity securely
- access demographics and analytics detailing how, when, and where users are logging in
- enrich user profiles from other data sources using customizable JavaScript rules

[Why Auth0?](https://auth0.com/why-auth0)

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more info.
