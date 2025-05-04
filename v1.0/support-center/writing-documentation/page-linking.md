---
type: page
title: Page Linking
listed: true
slug: page-linking
description: 
index_title: Page Linking
hidden: 
keywords: 
tags: 
---

Linking to pages (cross-referencing) is very powerful. As your documentation scales and changes, %product% automatically updates these references to ensure that the hierarchy of pages is always correct. Linking to pages applies between pages in one version.

{% callout type="success" title="Page or API" %}
You can link to a page or to an API reference - everything written here applies for both.
{% /callout %}

## Why Page Linking?

When a page is linked inside a version:

- The link will follow the page regardless of changes in documentation or page name.
- On cloning versions, the link will follow the page in the new version.
- You will be notified if a link breaks because a page was deleted.

## How to Link Pages

To create a link between pages, type `@` to open the pages selector.

{% image url="https://uploads.developerhub.io/prod/8gDX/ek10sm2dtv6cfa62s7qlpxhys3t03dss14i5rtn5ludwnbmco8802jzw45p8wixv.gif" caption="Pages selector open" mode="600" height="490" width="600" %}
{% /image %}

A list of all pages under the version will be listed for you to choose from. Search through the list by typing down the page name or slug. To select a page, click on its name in the list. If you are selecting an API Reference, then you will find the title of the API Reference.

{% callout type="info" title="External vs Page link" %}
External links in the editor show with a top-right pointing arrow so you can tell them apart from page links. The arrow will not show in live mode.
{% /callout %}

## Changing Link Title/Specifying Heading

After selecting the page, you will be prompted to change the link text (title). If you selected a page, you can link to a specific heading. If you selected an API reference, you can link to a specific operation.

**Note**: If you do not specify a title, then the title will _automatically_ update whenever the linked page title changes. For example, if you linked to page "Getting Started", and then you modified "Getting Started" page title into "Welcome", then the link text will automatically change to "Welcome".

{% image url="https://uploads.developerhub.io/prod/8gDX/ctn7vovlyu3g34vb2tog1v6vc9bclmbcpu3yur19es861nx27fc7w2flxegmq6ol.jpg" caption="Changing link title and specifying heading" mode="responsive" height="303" width="760" %}
{% /image %}

To navigate to a specific heading on the page, you can easily specify it. Begin typing to search for the desired heading in the selected page, or click on the arrow icon to display all available headings for easy access. Leaving **Heading** empty will default to the title of the page. The same goes for API references, where you can navigate to a specific operation.

Once you select a heading/operation, its URL fragment will appear. A fragment is the part of the link that is after the hash sign `#` . For example, the link `https://pied-piper.developerhub.io/v1.0/middle-compression/intro#how-to-use` has the fragment `how-to-use`.

Fragment can only contain alphanumeric characters and hyphens.

{% callout type="info" title="Info" %}
We do not monitor changes to the headings/operations. If a heading/operation is changed, then you should create the link again.
{% /callout %}

{% callout type="info" title="Keyboard Shortcut" %}
Did you know that you can follow the link when in editor mode by holding Shift +  ⇧  and clicking on the link?
{% /callout %}

## Analyse Links

Analysing links helps you understand the links that are:

- Broken because the linked page/reference was deleted.
- Leading to an unpublished page/reference from a published page.
- Navigating to an internal %product% link, instead of a link to your published docs.

## Listing Broken Links

If a link between pages or references is unreachable, you will be notified below the page title of the link analysis results. Link analysis runs automatically every time a page loads.

{% image url="https://uploads.developerhub.io/prod/8gDX/nf40ernu2bqn3bsrj6vkr60tidomp15787ydpp7n4akm6pmqubfysjss4xtodlej.jpg" caption="Broken link notification" mode="responsive" height="1058" width="2268" %}
{% /image %}

### Analyse Links for Entire Version

You can analyse all links in a version at once:

- In the sidebar, open Version {% icon classes="fas fa-code-branch inv-icon" /%}.
- Click on Analyse Links.

{% image url="https://uploads.developerhub.io/prod/8gDX/vg93bw8zuz3ftaijajjtc0ihucuqmdmtwl8nhx0s9bozjvnigmgd1qlbvoywwfix.jpg" mode="responsive" height="321" width="720" %}
{% /image %}

### View Broken Links in a Page

To view all the links analysis in a page, either click on the notification under the page title or:

- From the right sidebar, open Page Info {% icon classes="fas fa-file-alt inv-icon" /%}.
- View all broken links and link issues under Link Analysis.

{% image url="https://uploads.developerhub.io/prod/8gDX/xeervujy7634uaenu2s241mkb546n9hgyjqvwe5ps08wuxfrhnswhr93v4tm6u0l.png" mode="responsive" height="442" width="972" %}
{% /image %}

Every broken link will show you the title and the heading (if any) that it had before breaking. The list also shows the current text of the link so you are able to find it and fix it.

{% callout type="info" title="404 Page" %}
All broken page links will have the HREF of "/-" which leads to a 404 page.
{% /callout %}

{% callout type="info" title="Only Internal Links" %}
Only internal links created by using Page Linking are examined for breaking. The monitoring tool will not examine or alert about external links leading to 404.
{% /callout %}

## Listing Linked Pages (Backlinks)

If you are planning to delete a page, or modify the page heavily, then you might want to know what other pages are depending on this page. To list all pages linking to your current page:

- From the right sidebar, open Page Info {% icon classes="fas fa-file-alt inv-icon" /%}.
- Click on Get Links {% icon classes="fas fa-search" /%}.
- All links will be shown below, if any.

{% image url="https://uploads.developerhub.io/prod/8gDX/oz1wkfvj6s8tck0wzqpdxtfoayadmysh87z8z70o4vr8y5qn6qxlit2x5ydzgrgp.png" mode="responsive" height="380" width="331" %}
{% /image %}

## Page Permalinks

Permalinks are links that never change providing a reliable reference to a page.

To get a page permalink:

- From the right sidebar, open Page Info {% icon classes="fas fa-file-alt inv-icon" /%}.
- Click on the page ID just below the title.
- The link will be copied to your clipboard.

Our permalinks have the following structure: `https://<domain>/_permalink/<id>`.

{% callout type="warning" title="Warning" %}
Permalinks are dependent on the custom domain used. If the custom domain changes, the permalink will not be valid anymore.
{% /callout %}