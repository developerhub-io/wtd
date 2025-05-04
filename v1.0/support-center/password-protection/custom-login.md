---
type: page
title: Custom Login
listed: true
slug: custom-login
description: 
index_title: Custom Login
hidden: 
keywords: 
tags: 
---

Custom login for readers on %product% is facilitated through the use of JSON Web Tokens (JWT). By implementing JWT login, you can enhance security and streamline the authentication process. Here's how it works:

- You manage who can access your docs without needing to share a single password or link.
- You can [personalise](/support-center/personalised-docs) the docs for the logged-in reader.
- You decide when the access ends.

## How JWT Login works

When JWT (JSON Web Token) login is enabled, the login process follows a specific sequence of steps:

1. The reader might arrive at the docs site without being logged in and will be redirected to the login page, or they may start from your website to reach the login page.
2. When users reach the login URL, your backend servers will sign a JWT token with an [API Key](/support-center/api-key) that has `access.write` permission. They will then create a URL with the JWT token and redirect the user to it. This URL will point to your docs site.
3. If a reader tries to access the docs site without logging in and includes a JWT token in the URL, our backend servers will check the token and generate an access token that expires based on the token's settings. The reader can then access the docs site.
4. When the reader access token expires, they cannot access the content and will be redirected to the login URL to start the process again.

{% callout type="info" title="Info" %}
We provide the URL that the reader tried to access in a query parameter called `redirect`. Your servers can read this parameter and use it as the redirect URL instead of the landing page of your docs.
{% /callout %}

## How to enable JWT Login

To set up JWT login on %product%, follow these steps:

1. From the sidebar, choose Project Settings {% icon classes="fas fa-layer-group inv-icon" /%}.
2. Under General Settings, choose Make Private (or Manage Access).
3. Select JWT.
4. Provide a login URL, read more about [login URL](/support-center/password-protection#using-login-url) here.
5. Click Save.

{% image url="https://uploads.developerhub.io/prod/8gDX/9co9ui055800t232zqw4z16lbiprbui3xurkayb7ufrg4lmz4alu84cdhtpxwa0f.png" mode="responsive" height="966" width="1436" %}
{% /image %}

## Signing JWT

To access your docs site, you need to sign a JWT token using an [API Key](/support-center/api-key) with `access.write` permission. First, make sure you have generated the API Key. The supported signing algorithms are HS256 and HS512.

There are numerous libraries for most programming languages for signing JWT, see [jwt.io](https://jwt.io/) for details,

Example code to sign the JWT:

{% code %}
{% tab language="javascript" %}
const sign = require('jsonwebtoken').sign;
const apiKey = '689c3ce8e7c68b7c7f86acca6a028e6f8656eb792b19a334f8e3f2a56ca8f561';

function getSignedDeveloperHubUrl() {
  const docsUrl = 'https://docs.pied-piper.com'; // Your docs site URL. It may be a URL to a specific page or API Reference.
  const payload = {
    version: 1, // Controls the version of custom login. Do not remove.
    vars: { // Personalise documentation by injecting variables here if needed
      userId: 1234
    },
    error_redirect_url: 'https://pied-piper.com' // Optional: Redirects to this URL on error
  }; // Place here any variables you want to inject to personalise the docs.
  const expiresIn = 24 * 60 * 60; // Expiry, preferably 1 day, the shorter the more secure. Expiry must be defined.

  const token = sign(payload, apiKey, {expiresIn: expiresIn});

  return `${docsUrl}?jwt=${token}`;
}
{% /tab %}
{% /code %}

After the URL is created, you can send your reader the generated URL to give them access to the docs.

{% callout type="warning" title="Sign only in the backend" %}
To successfully sign a JWT (JSON Web Token), it is essential to have an API Key with the required `access.write` permission. Please remember that the API Key is a sensitive piece of information and must be kept confidential; it should never be shared publicly or stored in insecure locations.
{% /callout %}

To make it easier, you can generate a JWT directly from the Manage Access window by clicking on "Generate JWT" and choosing the expiry value.

## Example Express App

An example express app which you may use:

{% code %}
{% tab language="javascript" %}
const express = require('express');
const app = express();
const sign = require('jsonwebtoken').sign;
const port = 1234;

const apiKey = '689c3ce8e7c68b7c7f86acca6a028e6f8656eb792b19a334f8e3f2a56ca8f561';

function getSignedDeveloperHubUrl(url) {
  const docsUrl = url || 'https://docs.pied-piper.com';
  const payload = {
    version: 1,
    vars: {
      user: {
        id: 1234,
        name: "John"
      }
  	}
  };
  const expiresIn = 24 * 60 * 60;

  const token = sign(payload, apiKey, {expiresIn: expiresIn});

  return `${docsUrl}?jwt=${token}`;
}

app.get('/login', (req, res) => {
  res.redirect(getSignedDeveloperHubUrl(req.query.redirect));
});

app.listen(port, () => {
  console.log(`Reader login app listening at http://localhost:${port}`)
});
{% /tab %}
{% /code %}

## Limiting Access to One Device

To restrict a single JWT token to one device, add a unique `jti` in the payload. For example:

{% code %}
{% tab language="javascript" title="" highlightLines="4" %}
function getSignedDeveloperHubUrl(url) {
  const docsUrl = url || 'https://docs.pied-piper.com';
  const payload = {
    jti: require('uuid').v4(),
    version: 1,
    vars: {
      user: {
        id: 1234,
        name: "John"
      }
  	}
  };
  const expiresIn = 24 * 60 * 60;

  const token = sign(payload, apiKey, {expiresIn: expiresIn});

  return `${docsUrl}?jwt=${token}`;
}
{% /tab %}
{% /code %}

In this example, a UUID was utilized to ensure the uniqueness of the `jti` parameter. However, any random sequence can be employed to achieve the same purpose.

If the same JWT is utilized to access a project again, the reader will be denied access and will receive a message stating, "Token has already been used."

## Handling JWT Login Error

You can include an `error_redirect_url` in your JWT payload. If an error happens (like a token expiration or signature verification failure), the user will be sent to that URL with a query parameter `dh_jwt_error` that holds the error message.

## Reader Authentication through SSO/Cognito/Salesforce

To set up reader authentication using SSO, Cognito, Salesforce, or other identity providers, follow these steps:

1. Once the reader visits the docs site without being logged in, they will be directed to the login URL you set up in %product%.
2. The login URL is a page you host that handles authentication using SSO, Cognito, Salesforce, other identity providers, or your own login system. Users log in as they usually do on your systems.
3. If you want to let the user access the docs, you should [sign a JWT](/support-center/custom-login#signing-jwt) and then send the user back to the docs site with the token in the URL.

In summary: %product% does not connect directly with identity providers for reader authentication. Instead, it integrates through your backend systems, allowing for high customization and personalization of the docs for your users. If you have a login system in place, most of the reader authentication work is already done. You just need a new API GET endpoint (login URL) that signs the JWT.