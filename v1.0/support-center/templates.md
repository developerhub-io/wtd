---
type: page
title: Templates
listed: true
slug: templates
description: 
index_title: Templates
hidden: 
keywords: 
tags: 
---

If you find yourself writing pages with the same format and structure, then you can use Templates to simplify your experience.

{% image url="https://uploads.developerhub.io/prod/8gDX/i60etjiumq78ro0qaxlvkdwcobzuy3kn6hhj770jl5imwz27ef0zlavfg540tsgj.jpg" mode="responsive" height="806" width="1136" %}
{% /image %}

By using Templates, you can turn an existing page into a template, so the same format and structure can be applied to new pages.

## Create a Template

To create a template:

1. Select the page you want to make a template of or create a new one and save it.
2. Below the page title, click on {% icon classes="fas fa-archive" /%} to create a template from the page.
3. Give the template a title. The template would be saved now.

## Use a Template

To use a template:

1. Create a new page.
2. Under the page title, click on {% icon classes="fas fa-inbox" /%} Create from Template.
3. Select one of the existing templates you created. The template would be applied to the page.

## Delete a Template

To delete a template:

1. Create a new page.
2. Under the page title, click on {% icon classes="fas fa-inbox" /%} Create from Template.
3. Find the template you wish to delete, and click the {% icon classes="fas fa-times" /%} icon next to it.
4. Confirm your choice.

## Share a Template Link

If you regularly build pages from templates, you might want to use a template link. The template link loads the documentation, creates a new page at the bottom of the index, and loads up the template.

To do this, use the following link:

{% code %}
{% tab language="none" %}
https://app.developerhub.io/{project_slug}/{version_slug}/{documentation_slug}/new?create_from_template_id={template_id}

## Example from this documentation
https://app.developerhub.io/developerhub.io/v1.0/support-center/new?create_from_template_id=10
{% /tab %}
{% /code %}

Note that all parts of the link before `?` are the exact same as any page link you have open in the editor. If you load up the desired documentation in the editor, copy the link and add the query, that would be a template link.

Where `template_id` can be found when you are selecting a template at the top right corner:

{% image url="https://uploads.developerhub.io/prod/8gDX/vq41hoyu8cip00ta4i9v67joh32or8f0pobta6cn0pjpvqpt6r9qq6smuzrqggtw.png" mode="responsive" height="578" width="1044" %}
{% /image %}

## Known Limitations

{% callout type="error" title="Page Linking" %}
If a template has a [page link](/support-center/page-linking) in its contents, then the page link would only be valid for the version it was created in. You might want to create different template pages for different versions if you must have an internal page link in it.
{% /callout %}