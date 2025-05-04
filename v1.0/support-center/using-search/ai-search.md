---
type: page
title: AI Search
listed: true
slug: ai-search
description: 
index_title: AI Search
hidden: 
keywords: 
tags: 
---

Search by posing a question and receiving a natural, contextually appropriate response. This functionality leverages the advanced capabilities of OpenAI's GPT models.

{% callout type="warning" title="Free feature" %}
This feature is currently free, but we may charge for AI features in the future.
{% /callout %}

{% callout type="warning" title="Beta" %}
This is a beta feature. Your [feedback](/support-center/contact-us) is appreciated.
{% /callout %}

{% video videoId="https://uploads.developerhub.io/prod/02/nvrnanscgw7okyvlbqfcs8n1xmgxtc6h1cmr54i3e18avestnunznr12liyvk6gx.mp4?autoplay=true&loop=true&muted=true&playsinline=true&controls=false" provider="raw" %}
{% /video %}

## AI Search Features

{% glossary term="AI Search" /%} lets readers ask questions about the docs and receive answers powered by GPT, directly from the docs. Features of AI search:

- Answers from both documentation and API references.
- Can ask questions in any language, regardless if the documentation is written using that language or not.
- Responds using the language of the question.
- Provides a source list for further reading.

## AI Search Experience

When [AI Search is enabled](/support-center/ai-search#enabling-ai-search), the search bar will show "Search or ask a question" instead of just "Search." The AI search will turn on when the reader:

- Presses the enter key or,
- Types in text in a question form (such as start with "How" "Where" "Why") or,
- Types in a question mark or,
- Clicks on the AI prompt "Press enter to ask".

When the reader presses enter, the question will be answered using the available documentation, including explanations and examples if possible. The sources will be listed after the answer.

## Enabling AI Search

To enable or disable the AI search feature, follow these instructions:

- From the left sidebar, choose **Project Settings** {% icon classes="fas fa-layer-group inv-icon" /%}.
- Under AI Features, check or uncheck **Enable AI search**.

Once AI search is enabled, it may take a few minutes to become usable.

## Search Update Frequency

New or deleted content will be available for AI search within 30 minutes.

## Validating Responses

You can download a log of all questions and answers to validate responses from AI Search.

To download the log:

- From the left sidebar, choose **Project Settings** {% icon classes="fas fa-layer-group inv-icon" /%}.
- Under AI Search, click on the {% icon classes="fas fa-download" /%} icon.
- Select the duration to download the logs for.

The logs include a UID, which is an anonymous user identifier. It helps in understanding the various questions a user has asked.

## Limitations of AI Search

- Only indexes and displays on the default version of the documentation.
- Prone to give wrong, unclear, or incomplete answers.
- No analytics have been collected so far.
- AI Search only works on [Next UI](/support-center/customising-visuals#next-ui).

## What data is sent to OpenAI?

When enabling AI search for a project, all content accessible to readers is transmitted to OpenAI. Additionally, each time the content is re-indexed, any new or updated content will also be sent to OpenAI.