---
type: page
title: Using Markdown
listed: true
slug: using-markdown
description: 
index_title: Using Markdown
hidden: 
keywords: 
tags: 
---

### What is Markdown?

Markdown is a [lightweight markup language](https://en.wikipedia.org/wiki/Lightweight_markup_language) with plain text formatting syntax. It is widely used for formatting README files, documentation, and comments all around the web. Using it is simple and fast.

### How to use Markdown?

If you are a technical person, then you'd probably love to be able to write your documentation in Markdown.

%product% supports Markdown seamlessly. Write in Markdown and we will transform it right away.

{% image url="https://uploads.developerhub.io/prod/8gDX/fsrnxazmnr81jrxnz5h1bcfp2tvai9366o7mpb3j6gb02lqabrdils55bw1su77z.gif" caption="Instant markdown formatting" mode="300" height="228" width="300" %}
{% /image %}

We currently support:

- Heading 2, Heading 3 and Heading 4 using `## H2`, `### H3` and `#### H4`
- Bold text using `**text**`
- Italic text using `*text*` or `_text_`
- Links using `[title](URL)`
- Code blocks by starting a line with triple quotes
- Inline code by surrounding text with backticks (`)
- Callouts by starting a line with `>` and a space
- Separators by starting a line with `---`
- Unordered lists by starting a line with `*` or `-` and a space
- Ordered lists by starting a line with `1.` and a space. You can also continue numbering by starting a line with any number, a dot then a space.
- Tables by starting a line with `|` and a space

{% callout type="info" title="Nested Lists" %}
Lists can be indented and outdented using Tab and Shift+Tab.
{% /callout %}

{% callout type="info" title="Escaping back tick (`)" %}
To escape back tick, you need to [disable live markdown formatting](/support-center/using-markdown#disable-live-markdown-rendering) and type two back ticks, your expression, then two back ticks. For example: ``abc ` def``
{% /callout %}

## Pasting Markdown

If you are pasting raw Markdown from an external source, then it might not render immediately. Do not worry. Once you save the page and refresh it, formatting will render correctly. Note that this does not work for code blocks or tables.

## Disable Live Markdown Rendering

If Markdown live rendering is getting in your way when having content alike to Markdown, then you can disable Live Markdown Rendering from your Account Settings.

## More Markdown?

Talk to us and tell us what you need!