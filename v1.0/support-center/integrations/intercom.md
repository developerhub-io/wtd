---
type: page
title: Intercom
listed: true
slug: intercom
description: 
index_title: Intercom
hidden: 
keywords: 
tags: 
---

Users of the Supercharged plan have the capability to seamlessly integrate %product% with Intercom. This integration enables direct communication with their users and allows the addition of a documentation search widget in the messenger home, enhancing user experience and support accessibility.

{% image url="https://uploads.developerhub.io/prod/8gDX/cvmw2u007lnm7ab1i7opr9dr8qce8806auja2irskak4cg0jtjpf4m5lgpynt321.png" mode="300" height="1330" width="300" %}
{% /image %}

## Setting up Intercom

- Click on Project Settings {% icon classes="fas fa-layer-group inv-icon" /%} in the sidebar to access Intercom settings under Integrations for Customers.
- Click Connect. You will go through a process to install the %product% app on Intercom.

{% callout type="success" title="All set up!" %}
The Intercom widget will now appear in your published documentation.
{% /callout %}

{% image url="https://uploads.developerhub.io/prod/8gDX/6cxxaxdt5fenc7i78ak7v6x3y3a5bxpq4npn7xmy9al1l0xio7aarollmqw2ggoa.png" mode="600" height="1252" width="600" %}
{% /image %}

## Adding Search Widget

{% callout type="warning" title="Installed Intercom before 12 Aug 2023?" %}
If you installed Intercom on %product% before August 12, 2023, please [contact us](/support-center/contact-us) to add the search widget.
{% /callout %}

{% callout type="info" title="Only in Default Layout" %}
Intercom can only show widgets with the default layout messenger, not with the compact layout.
{% /callout %}

To add a %product% search widget to your messenger home, make sure you have [set up Intercom](/support-center/intercom#setting-up-intercom). Then:

- From Intercom's platform, click on Messenger & Omnichannel in the sidebar.
- Under Messenger, click on Manage Settings.
- Under Customise Home with apps, click on Add an app.
- Choose %product%.
- Change the card title if needed.

{% image url="https://uploads.developerhub.io/prod/8gDX/6hitr7qm2mlg52iv1n7wy9jjigknypa3pfpd09erp3plky0cwsxoyuk0305bk8ou.png" mode="300" height="1700" width="300" %}
{% /image %}

## Changing Intercom Region or Settings

To set your own `intercomSettings`, including changing the data region, use [auto$](/support-center/custom-javascript). Add a script tag to assign the required `intercomSettings`, like this:

{% code %}
{% tab language="json" %}
<script>
  window.intercomSettings = {
    api_base: "https://api-iam.eu.intercom.io"
  };
</script>
{% /tab %}
{% /code %}