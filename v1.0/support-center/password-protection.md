---
type: page
title: Private Documentation
listed: true
slug: password-protection
description: 
index_title: Private Documentation
hidden: 
keywords: visitor auth, visitor authentication, guest authentication, guest auth
tags: 
---

Supercharged plans enable administrators to set their documentation portal to private, effectively restricting access to anyone on the internet. The protected project can only be viewed by:

- Visiting the documentation site, and entering a [shared password](/support-center/password-protection#password-protect-set-up).
- Opening a [shared link](/support-center/password-protection#link-sharing).
- Invited readers through [magic links](/support-center/email-invite).
- [Custom login](/support-center/custom-login) flow using JSON Web Tokens (JWT).

If you are subscribed to our enterprise plan, we offer enhanced reader authentication via your intranet to ensure secure access for your users.

## Comparison Between Different Methods

{% table %}
| Method | Security Level | Ease of Access | Needs a Developer? | Usage | 
| ---- | ---- | ---- | ---- | ---- | 
| [Password](/support-center/password-protection#password-protect-set-up) | Weak. Your readers might leak the password. | Need to remember a password | No | Use to block out competitors and crawlers. | 
| [Shared Link](/support-center/password-protection#link-sharing) | Weak. Your readers might leak the link. | Easy, click on a link. | No | Use to block out competitors and crawlers. | 
| [Reader Magic Link](/support-center/email-invite) | Strong | Easy, readers goes to the docs site, requests a magic link and opens the link. | No | Use to secure data and control access. | 
| [Custom Login](/support-center/custom-login) | Strong | Easy, reader needs to go to the docs site, but might need to log into your own site. | Yes | Use to secure data, control access and [personalise](/support-center/personalised-docs) docs. | 
| Intranet (Enterprise only) | Strong | Easy, reader just needs to go to the docs site. | Yes | Use to secure data and control access. | 
{% /table %}

## Password Protect Set up

To set up password protection:

- Go to your Project Settings {% icon classes="fas fa-layer-group inv-icon" /%} from the sidebar.
- Click on Make Private (or Manage Access).

{% image url="https://uploads.developerhub.io/prod/8gDX/36r7557zmvuk41bsn5fllmhhcpn9x4tmskcziiduf7fpj0j75tjqqt3dzltsyzgx.png" mode="set" height="814" width="448" %}
{% /image %}

- Choose Password.
- Input the password.
- Click on Save.

{% image url="https://uploads.developerhub.io/prod/8gDX/ifxphy74ecad6jdken0h03t3sa5vnzpni9i7m57fipc7me7hf2hn6ziwsvgwcbkt.png" mode="responsive" height="1088" width="1424" %}
{% /image %}

{% callout type="success" title="Success" %}
Great, all the published pages of this project are now protected by a password
{% /callout %}

To see it in action, go to the live mode of your documentation. You will see a page like this.

{% image url="https://uploads.developerhub.io/prod/8gDX/n8snlrzeprxm4gd5un6m0qqf92gmw2offjfrhx7w9ok40tyz7iofmgshn22tvhrb.jpg" mode="responsive" height="1698" width="2276" %}
{% /image %}

Once a reader enters the correct password, they will stay logged in for 24 hours.

{% callout type="warning" title="Warning" %}
It is strongly advised against saving confidential or sensitive information in a password-protected project. The primary purpose of a password protection mechanism is to restrict access to certain users, but it does not guarantee the security of the data. Relying on password protection alone could inadvertently expose your information to the general public and search engines. Always ensure that sensitive data is stored securely using appropriate encryption methods and data protection measures.
{% /callout %}

## Link Sharing

Once a project is password-protected, you can share a link that allows access without entering a password. This feature lets you give your customers read access by sharing the link with them internally.

To share a link:

- Open Project Settings {% icon classes="fas fa-layer-group inv-icon" /%}
- Next to Manage Access, click on Share Link {% icon classes="fas fa-share-alt" /%} icon.

{% image url="https://uploads.developerhub.io/prod/8gDX/5l7l3lkzoxgrfbskdwm5ul7jf4dletsxxrknn44zato4f5uq1r1k21i6ssyzqohd.png" mode="set" height="790" width="478" %}
{% /image %}

- You can send invitations directly to your readers. Separate e-mail address by using commas.
- Or you can copy the link and paste it.

{% callout type="warning" title="Warning" %}
The link will be canceled if the password is changed or deleted.
{% /callout %}

## Using Login URL

If your docs are protected with a [shared link](/support-center/password-protection#link-sharing) or a [custom login flow](/support-center/custom-login), your readers will likely need to log in to your website. To make this easier, you can redirect unauthenticated readers to a URL of your choice, where:

- If you're using secure link sharing, it will take users to the page where they can find the link, or redirect them to the link if they are logged in to your website.
- If you use [custom login](/support-center/custom-login), it will take them to a login page. If they are already logged into your website, they will be redirected back to the docs site. Otherwise, they will be asked to log in first.

To setup login URL:

- Go to Project Settings {% icon classes="fas fa-layer-group inv-icon" /%} in the sidebar.
- Click on Manage Access.
- Under Login URL, input the URL. An example would be `https://pied-piper.com/docs-login`.

### Disabling Protection

To disable password protection:

- Go to Project Settings {% icon classes="fas fa-layer-group inv-icon" /%} in the sidebar.
- Click on Manage Access.
- Choose Public {% icon classes="fas fa-unlock" /%}

Immediately, the project will be unprotected.

{% callout type="warning" title="Warning" %}
All your published versions will stay published. If there are versions you don’t want the public to access, remember to unpublish them before unprotecting the project if necessary.
{% /callout %}