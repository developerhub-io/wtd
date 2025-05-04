---
type: page
title: Preview Documentation
listed: true
slug: previewing-documentation
description: 
index_title: Preview Documentation
hidden: 
keywords: 
tags: 
---

%product% is designed to unify the view between the editor and the live version.

You do not need to preview your documentation. The editor shows you your documentation in a rendered state so that when you edit then you can see how changes will look for your documentation users 🤯

{% callout type="success" title="Woah!" %}
What was I thinking before?!
{% /callout %}

If you still want to preview your documentation, then you can publish the documentation for a live view.

## URL Strategy

The URL, which is the link in the browser, indicates which project, version, and section (documentation or API reference) that your users are accessing. With an organized URL strategy, you provide a predictable navigation experience across different parts of the documentation for your users.

Here is a summary of how resources are loaded using URLs:

{% table widths="388" %}
| URL | Result | 
| ---- | ---- | 
| `https://<project>/<section>` | Loads the default page in the specified documentation, or the specified API reference in the default version. | 
| `https://<project>/<documentation>/<page>` | Loads the page in the specified documentation in the default version | 
| `https://<project>/<version>/<section>` | Loads the default page in the specified documentation, or the specified API reference in the specified version | 
| `https://<project>/<version>/<documentation>/<page>` | Loads the specified page in the specified documentation in the specified version | 
| `https://<project>/` | Loads the landing page if enabled, or the default page in the default section of the default version | 
{% /table %}

The following URLs are deprecated and not recommended for use; however, for backward compatibility, they are redirected:

{% table %}
| URL | Redirected To | 
| ---- | ---- | 
| `https://<project>/<version>/-/-` | `https://<project>/<version>/<documentation>` | 
| `https://<project>/<version>/<documentation>/-` | `https://<project>/<version>/<documentation>` | 
| `https://<project>/<reference>/ref` | `https://<project>/<reference>` | 
| `https://<project>/<version>/<reference>/ref` | `https://<project>/<version>/<reference>` | 
| `https://<project>/-/-/-` | `https://<project>/<section>` | 
{% /table %}

Any other form of link will load the default page.

You can add a base path if you are [hosting under your own existing website](/support-center/hosting#hosting-under-your-own-custom-domain). The same rules apply, but the base path will be added right after the `<project>`. For example, instead of `https://<project>/<version>/<documentation>/<page>`, the link would be `https://<project>/<base-path>/<version>/<documentation>/<page>`.

## Print-Optimized

Pages are print-optimized (specially for A4 paper size). When printing, use the wide documentation layout and always print from the published documentation site (not from the editor). If you are an enterprise customer, then you may also [export an entire version as PDF](/support-center/pdf-export).

{% image url="https://uploads.developerhub.io/prod/8gDX/3lmhzjyqdyxlpxseucjwoqcesxxee9u0u2843iodjlbf7dm5shwebyl6svraln6v.jpg" mode="responsive" height="2270" width="2832" %}
{% /image %}

## Embed Mode

%product% sites can be embedded using `iframe` as needed. This is helpful if you want to create a documentation widget so your users can follow the instructions without leaving their tabs.

There are two types of embed mode:

- Minimal: Hides the top navigation, footer, index, and table of contents. Mode is `embed`.
- Normal: Hides the top navigation and footer only. Mode is `embed_full`.

{% callout type="info" title="Note" %}
In scenarios where the window width is small, minimal and normal modes exhibit similar behavior. This is because both the index and the table of contents are hidden by default when the window width is reduced.
{% /callout %}

Embed mode can be turned on by adding a `?mode=embed` or `?mode=embed_full` to any %product% URL (except landing pages). For instance, to show users the page at `[https://dev.company.io/ios/getting-started](https://dev.company.io/ios/getting-started)`, you can load an `iframe` with `src="[https://dev.company.io/ios/getting-started?mode=embed"](https://dev.company.io/ios/getting-started?mode=embed&quot;)`.

{% code %}
{% tab language="markup" title="HTML" %}
<iframe style="position:fixed;width: 500px;height: 450px;background: white;right: 100px;bottom: 0px;z-index: 10;border: 1px solid #bbb;border-radius: 5px;" src="https://docs.developerhub.io/support-center/uploading-references?mode=embed"></iframe>
{% /tab %}
{% /code %}

Here is a preview:

{% image url="https://uploads.developerhub.io/prod/8gDX/1woh5xa6urcb2hchq5a5mo5dg4dstqkepelmdm1758d6jyxqrr5azl1hlapda7n5.png" mode="responsive" height="1755" width="3112" %}
{% /image %}