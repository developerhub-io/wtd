---
type: page
title: Custom Landing Page
listed: true
slug: custom-landing-page
description: 
index_title: Custom Landing Page
hidden: 
keywords: 
tags: 
---

{% html %}
<div class="grow-border text-left">
<div class="grow-star">⭐</div>
    Available in Grow Projects
</div>
{% /html %}

For enhanced control and branding of your landing page, you can use HTML, CSS, and JavaScript to create a bespoke landing page tailored to your unique needs.

{% image url="https://uploads.developerhub.io/prod/8gDX/62s0vzv9suxgpc3ioxlaugzdy8qujbs1yotd2hxq39fg0gpmgp1ilnoa7mkri116.jpg" caption="Our Custom Landing Page" mode="responsive" height="1189" width="1501" %}
{% /image %}

## Use Custom Landing Page

To enable a custom landing page for the main landing page:

- Open the Landing Page from the sidebar {% icon classes="fas fa-rocket inv-icon" /%}
- Select the main landing page.
- Click on the {% icon classes="fas fa-cog" /%} settings icon at the top.
- Click on **Enable** next to Use Custom Page.

To modify the landing page HTML:

- Click **Edit HTML**.

- Paste or type in the HTML to make your custom landing page. Click Save. This will save the HTML in draft mode so that you can test it out.
- To publish it to readers, click Save & Publish.
- To revert the draft changes, click Revert.

{% callout type="warning" title="Write body only - Not full HTML page" %}
The HTML you provide will be inserted into the body of the landing page in a div with `landing-page-container` class. Thus, do not wrap everything in `<html>` tag. `<head>` tag will also be discarded. See our examples [below](/support-center/custom-landing-page#mocking-default-landing-page).

This also apply to `<style>`. All styles should be moved to [Custom CSS](/support-center/custom-css).
{% /callout %}

## Crafting a Landing Page

{% image url="https://uploads.developerhub.io/prod/8gDX/cg8l0luz1apglog6zv8iao7bu7cdhonjqqy082mocd1iki3bw6hn4mm5kcreig35.jpg" caption="Customize HTML for the Landing Page" mode="responsive" height="507" width="914" %}
{% /image %}

When customizing the landing page, you have the option to enter HTML code, which will be inserted asynchronously into your landing page. 

{% callout type="warning" title="Unvalidated HTML" %}
Note that we do not evaluate or validate the HTML inserted - please double check that it is valid.
{% /callout %}

## Adding CSS

To add CSS to improve your website or application, you have several options:

- You can add your custom styles directly to [Custom CSS](/support-center/custom-css).
- You can include your CSS styles in the [Custom HEAD Tags](/support-center/custom-javascript) section by wrapping them in a `<style>` tag.

- If you prefer to use an external stylesheet, link to the CSS file with a `<link>` tag for easier organization and maintenance of your CSS rules.

{% code %}
{% tab language="css" %}
<link rel="stylesheet" type="text/css" href="MyCustomeCSSFile.css"/>
{% /tab %}
{% /code %}

{% callout type="warning" title="Global CSS" %}
Remember that the CSS is applied globally. Modifying classes of conventional names (specially Bootstrap selectors), such as `.container` might have unwanted effects.
{% /callout %}

## Adding Javascript

If you wish to add Javascript, then you can add it in [Custom HEAD Tags](/support-center/custom-javascript) in a `<script>` tag. If you wish to reuse the [cards](/support-center/landing-page) from our original landing page, then you can listen to a dedicated event `oncardschanged` as such:

{% code %}
{% tab language="html" %}
<script>
document.addEventListener('oncardschanged', function (event) {
  console.log("cards changed", event);
});
</script>
{% /tab %}
{% /code %}

This event also indicates that the landing page HTML has already loaded, and that you can query its selectors.

The event output looks like the follows for the main landing page:

{% code %}
{% tab language="json" %}
CustomEvent {
  "detail": {
    "sectionType": "landing-page"
    "docs": [
      {
        "title": "Start Here",
        "link": "/support-center",
        "details": [
           {"title": "Getting Started", "link": "/support-center/getting-started"},
           {"title": "Writing Documentation", "link": "/support-center/writing-documentation"},
           {"title": "Structuring Documentation", "link": "/support-center/structuring-documentation"}
        ]
      },
      {
        "title": "Blocks",
        "link": "/support-center",
        "details": [
           {"title": "Code Blocks", "link": "/support-center/code-blocks"},
           {"title": "Callouts", "link": "/support-center/callouts"},
           {"title": "Images", "link": "/support-center/images"}
        ]
      },
    ],
    "refs": [
      {
        "title": "API", 
        "link": "/api"
      }
    ]
  }
}
{% /tab %}
{% /code %}

For a non-main landing page, the detail would be as such:

{% code %}
{% tab language="json" %}
CustomEvent {
  "detail": {
    "sectionType": "custom-page",
    "sectionId": 612
    "docs": [
      {
        "title": "Start Here",
        "link": "/support-center",
        "details": [
           {"title": "Getting Started", "link": "/support-center/getting-started"},
           {"title": "Writing Documentation", "link": "/support-center/writing-documentation"},
           {"title": "Structuring Documentation", "link": "/support-center/structuring-documentation"}
        ]
      },
      {
        "title": "Blocks",
        "link": "/support-center",
        "details": [
           {"title": "Code Blocks", "link": "/support-center/code-blocks"},
           {"title": "Callouts", "link": "/support-center/callouts"},
           {"title": "Images", "link": "/support-center/images"}
        ]
      },
    ],
    "refs": [
      {
        "title": "API", 
        "link": "/api"
      }
    ]
  }
}
{% /tab %}
{% /code %}

Where `sectionId` is an identifier you may use to customise what elements are added to which landing page.

## Linking to Content

To navigate to content in the documentation from your landing page, use absolute paths. When using absolute paths, the navigation would be done internally in the single-page application, rather than a full-slow navigation. For example:

{% code %}
{% tab language="markup" title="HTML" %}
<a href="/support-center/getting-started">
  Getting Started
</a>
<!-- If your project has a basepath (e.g. docs), include it -->
<a href="/docs/support-center/example-requests">
  Example Requests
</a>

<!-- ❌ do not use for internal navigation -->
<a href="https://docs.example.com/support-center/getting-started">
  Example Requests
</a>
{% /tab %}
{% /code %}

If you are creating the content dynamically using Javascript, you can use `window.applyClickHandlersOnLinks()` at the end of your javascript (when all anchors have been added) to make all absolute path links navigate internally:

{% code %}
{% tab language="javascript" %}
const anchor = document.createElement('A');
anchor.href = "/support-center/getting-started";

window.applyClickHandlersOnLinks();
{% /tab %}
{% /code %}

{% callout type="warning" title="Deprecated" %}
Previously, `openLink` function used to handle opening internal links. This is no longer required and such functions can be removed.
{% /callout %}

## Tips & Tricks

### Hiding Top Navigation Bar

If you wish to hide the top navigation bar when on the custom landing page, you can do that using Javascript:

{% code %}
{% tab language="html" %}
<script>
	document.addEventListener('onsectionchange', function (event) {
        switch (event.detail.type) {
            case 'landing-page':
                document.querySelector("app-top-nav").style.display = "none";
                break;
            default:
                document.querySelector("app-top-nav").style.display = "inline";
            }
    });
</script>
{% /tab %}
{% /code %}

## Mocking default Landing Page

Our own custom landing page available at [https://docs.developerhub.io](https://docs.developerhub.io) includes the cards which exist in the default contents of the landing page. In order to mimic this layout, you may use the following code (works for single version, single documentation projects) - or modify it to fit your needs:

{% code %}
{% tab language="html" title="HTML" %}
<div class="container">
  <div class="row">
    <div class="col">
      <h4 style="border-bottom: 3px solid #ff536b; border-radius: 1px; display: inline-block; margin-bottom: 64px; line-height: 2;">
        Browse through our documentation
      </h4>
    </div>
  </div>
  <div class="row" id="landing-cards">
  </div>
</div>
{% /tab %}
{% tab language="javascript" %}
document.addEventListener('oncardschanged', function (event) {
  if (event.detail.sectionType !== "landing-page") {
    return;
  }
  const cardsContainer = document.querySelector('#landing-cards');
  event.detail.docs.forEach((card) => {
    const cardDiv = document.createElement('DIV');
    cardDiv.classList.add('landing-card', 'docs-card');
    cardDiv.addEventListener('mouseenter', ev => {cardDiv.classList.add('show-hovered')});
    cardDiv.addEventListener('mouseleave', ev => {cardDiv.classList.remove('show-hovered')});

    const titleAnchor = document.createElement('A');
    titleAnchor.classList.add('clickable');

    const h4CardTitle = document.createElement('H4');
    h4CardTitle.classList.add(['title']);
    h4CardTitle.innerText = card.title;

    titleAnchor.href = card.link;
    titleAnchor.appendChild(h4CardTitle);
    cardDiv.appendChild(titleAnchor);

    card.details.forEach((cPage) => {
      const aLink = document.createElement('A');
      aLink.classList.add('d-block', 'link', 'clickable');
      aLink.href = cPage.link;
      aLink.innerText = cPage.title;
      cardDiv.appendChild(aLink);
    });

    rowSeparator = document.createElement('DIV');
    rowSeparator.classList.add('col-xs-12', 'col-sm-6', 'col-lg-6');
    rowSeparator.appendChild(cardDiv);

    const showAllA = document.createElement('A');
    showAllA.href = card.link;

    const showAllDiv = document.createElement('DIV');
    showAllDiv.classList.add('show-all');
    showAllDiv.innerHTML = 'Show all<i class="fas fa-chevron-right"></i>';
    showAllA.appendChild(showAllDiv);
    cardDiv.appendChild(showAllA);

    cardsContainer.appendChild(rowSeparator);
  });
  
  window.applyClickHandlersOnLinks();
});
{% /tab %}
{% /code %}

The CSS is unchanged.
