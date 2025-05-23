---
type: page
title: Server Headers
listed: true
slug: server-headers
description: This document provides guidance on configuring server headers for your documentation site.
index_title: Server Headers
hidden: 
keywords: server headers, security headers, content security policy, CSP, HTTP headers, strict transport security, X-Frame-Options, Referrer-Policy, nonce, custom headers, docs hosting, security configuration
tags: security
---


You may want to set up extra server headers for security purposes. The headers are returned when a client requests your docs site.

## How to set up Server Headers?

To set up server headers:

- From the sidebar, click on Project Settings {% icon classes="fas fa-layer-group inv-icon" /%}.
- Under Hosting, click on Edit Headers {% icon classes="fas fa-server" /%}.
- Add the server headers as follows:
    - Each header must be on one line.
    - Each header must have the header name and value separated by `:`.
    - You cannot modify certain headers, such as `Cache-Control` or `Server`.
    - Any invalid header will be removed.

- Hit Save.

It may take up to 5 minutes for changes to take effect.

## Example Security Headers

These are some security headers that you may want to apply.


{% callout type="warning" title="Caution" %}
Make sure you fully understand each header. Using headers incorrectly could cause your entire custom domain to be irreversibly broken. We are not liable for any damages due to misconfiguration.
{% /callout %}



{% code %}
{% tab language="yaml" title="Headers" %}
Strict-Transport-Security: max-age=31536000
X-Frame-Options: DENY
Referrer-Policy: no-referrer
{% /tab %}
{% /code %}


## Content Security Policy

Content security policy (CSP) can be set up using Server Headers.


{% callout type="warning" title="Warning" %}
Content security policy should only be configured by security professionals. Any misconfiguration might break your docs site or limit features. Furthermore, expect that you should keep updating the content security policy as %product% advances with new features.
{% /callout %}


To enable inline styles and scripts, you must add a nonce configuration for `style-src`  and `script-src` directives. The nonce configuration must be `nonce-%NONCE%` where our backend servers will replace `%NONCE%` for every session with a random nonce.

An example starter content security policy for projects is:


{% code %}
{% tab language="ruby" title="Content Security Policy" %}
default-src 'self';
script-src 'self' 'nonce-%NONCE%' https://files.developerhub.io;
style-src 'self' 'nonce-%NONCE%' https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css https://files.developerhub.io;
base-uri 'self';
connect-src 'self' https://api.developerhub.io https://ai.developerhub.io https://sentry.io https://*.algolia.net https://*.algolianet.com https://*.algolia.io https://www.google-analytics.com;
img-src 'self' https://static.developerhub.io https://uploads.developerhub.io https://files.developerhub.io https://image-archive.developerhub.io;
font-src 'self' https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/webfonts/fa-solid-900.woff2 https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/webfonts/fa-regular-400.woff2
https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/webfonts/fa-brands-400.woff2 https://fonts.gstatic.com;
frame-src 'self';
base-uri 'self';
object-src 'none';
{% /tab %}
{% /code %}


Modify as needed for your security and project needs.

You may also add `nonce=%NONCE%` in your [custom footer](/support-center/custom-footer) to apply style in the head tags.

