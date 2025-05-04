---
type: page
title: Personalised Docs
listed: true
slug: personalised-docs
description: 
index_title: Personalised Docs
hidden: 
keywords: 
tags: 
---

You can customize the docs for your readers, making it easier for them to find the information they need without switching between different sources.

Here are some things in your docs that can be personalized:

- User ID,
- User Name,
- API Keys,
- API version they're currently using,
- Plan they are on,
- Their permissions...

## How to Personalize Docs

You can use [variables](/support-center/variables) to personalize the docs for your readers. For example, if you accessed this documentation through Help & Support, you would see your name %user.name% on the first page and here as well.

Variables can be injected into the docs in two ways:

- By sending your readers to a docs URL having certain query parameters.
- By writing a [cookie](/support-center/personalised-docs#personalising-through-cookie).
- By using a [custom login](/support-center/custom-login) flow.

When the variables are injected, the documentation will dynamically display the information that is most relevant to the reader.

## Personalizing through URL

Variables can be injected into a page through the URL. You can provide the variables in two ways:

- Clear text: Add it in a URL query `vars`. For example `?vars={"user":{"name": "John"}}`
- Base64: Add it in a URL query `hvars`. For example `?hvars=eyJ1c2VyIjp7Im5hbWUiOiJKb2huIn19`

As an example, if you load this documentation from this link:

[https://docs.developerhub.io/?vars={"user":{"name": "John"}}](https://docs.developerhub.io/?vars=%7B%22user%22:%7B%22name%22:%22John%22%7D%7D)

{% callout type="info" title="Info" %}
The variables added through the URL will be saved for the user's session. They will remain until the browser is closed.
{% /callout %}

You will be welcomed as a person named John.

## Personalizing through Cookie

You can customize your site by setting a cookie that your docs site can read. Using a cookie for personalization is better than using URL personalization because the variables won't be visible in the URL box.

The cookie should be set on the main site, not just on the docs site. For example, if your main site is `pied-piper.com` and your docs are at `pied-piper.com/docs`, set the cookie on `pied-piper.com` so it can be accessed from `pied-piper.com/docs`.

Cookies can only be read on the same root domain, even if you're using subdomains. For example, you can set a cookie on: `pied-piper.com` and make it accessible on `docs.pied-piper.com` and `pied-piper.com/docs`. However, if your documentation site is on a different root domain like `pied-docs.com`, you need to personalize using [URL or custom login](/support-center/personalised-docs#how-to-personalise-docs).

To inject variables with a cookie, include the following in the cookie:

{% code %}
{% tab language="none" %}
Name: vars
Value: eyJ1c2VyIjp7Im5hbWUiOiJKb2huIn19 # Base64 of the variables JSON
Domain: .docs.pied-piper.com # Custom domain of your docs
Path: / # Basepath of your docs, if you have multiple projects on same custom domain
Expires: Thu, 18 Dec 2022 12:00:00 UTC # As needed
HttpOnly: false
Secure: true
SameSite: Lax
{% /tab %}
{% /code %}

For example, to create a cookie using JavaScript:

{% code %}
{% tab language="javascript" %}
let vars = {"user": {"name": "John"}};

document.cookie = "vars=" + btoa(JSON.stringify(vars)) + "; expires=Thu, 18 Dec 2022 12:00:00 UTC; path=/; domain=docs.pied-piper.com; SameSite=lax; Secure";
{% /tab %}
{% /code %}

## Standard for User Details

To personalize docs, we suggest using this standard for any current or future features. Please follow this JSON structure:

{% code %}
{% tab language="javascript" %}
{
  "user": {
    "id": 8
    "email": "email@address.com",
    "name": "User Name"
	}
}
{% /tab %}
{% /code %}