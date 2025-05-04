---
type: page
title: Search
listed: true
slug: using-search
description: 
index_title: Search
hidden: 
keywords: 
tags: 
---

%product% provides two search experiences:

- [Standard Search](/support-center/using-search#standard-search): Lightning-fast search service available for all paid plans. It searches all sections of the documentation and provides direct links to relevant results, even if there are typos.
- [auto$](/support-center/ai-search): Search using GPT models that give answers in easy-to-understand language and include sources.[auto$](/support-center/ai-search)

The search bar is prominently positioned at the top of the pages to capture attention and provide readers with an optimal browsing experience.

{% image url="https://uploads.developerhub.io/prod/8gDX/cij3np5n414jzp5j5mtoja6f5ziutcr0jjw4ndajoeentgbkw0p53gw2cgmer0lr.png" mode="responsive" height="335" width="734" %}
{% /image %}

### Look and Feel

The shadow of the search bar and the highlighting of the results utilize the same branding color that you have specified in [Customising Visuals](/support-center/customising-visuals#changing-colour). This ensures a cohesive and visually appealing interface that aligns with your brand identity.

{% callout type="info" title="Only in live mode" %}
Search functionality is exclusively available in live mode. While the search bar is visible in editor mode, it serves only as a demonstration and cannot perform actual searches. If you need to search for a specific page while in edit mode, please utilize the [Quick Switcher](/support-center/quick-switcher) instead.
{% /callout %}

## Next UI Search

[Next UI](/support-center/customising-visuals#next-ui) offers an improved search experience for readers. The search expands into a larger area and includes options for users to choose their search scope.

## Standard Search

Our standard search offers a lightning-fast experience, delivering relevant content that corresponds to the search terms entered by readers.

### Search Speed

Our lightning-fast search feature boasts an impressive average latency of under 10 milliseconds, ensuring swift and efficient results for your queries.

### Search Update Frequency

We update the search index every 15 minutes. This means if you add or remove content, it may take up to 15 minutes for the changes to appear in search.

## Page Keywords

You can enhance the visibility of your page by incorporating relevant keywords that will assist readers in discovering it through search queries. Keywords are most effective when they are not already present in the content of the page. Here are some examples of effective page keywords:

- Synonyms of words in the page.
- Words related to the page contents.
- Expansion of acronyms.

You can add page keywords from the Page Info {% icon classes="fas fa-file-alt" /%} toolbar on the right side of the page.

## Change Search Scope

To change the search scope to just the active documentation or API reference, check out `search.scope` in our [auto$](/support-center/advanced-settings).

## Searching using URL

To set up a search engine in your documentation or provide your readers with a search URL, add a `s` search query to any URL in your docs site. For example, using this URL format: `https://<your-project-domain>/?s=%s`, you can perform a search on a term (replace `%s`) as soon as the page loads.

## Advanced Search Operators

Searching has the support for two advanced operators:

- To find exact matches, use double quotations around the terms. For example: `"search engine"` will only match when the words "search engine" appear together and in that order.
- Minus: Prevent records that start with a minus sign. For example: `search -engine` will only match records containing search, but not engine.

## Best Practices For Searchable Content

To ensure that the search functionality effectively identifies and delivers what the reader is looking for, it is crucial to organize the content of your documentation thoughtfully. Therefore, consider structuring your documentation in the following manner:

- We divide search results using heading 2 only. Make sure your heading 2 sections are of moderate length. If any heading 2 content exceeds 10,000 characters (about 2,000 words or 100 sentences), it will be cut off.
- The text cannot be simplified while incorporating all the synonyms requested.

## Search using API

If you want to offer documentation search options outside of DeveloperHub, you can use our [Search](/v1.0/api/ref#search) to make queries and guide your users to the correct documentation. An example search request would be:

{% code %}
{% tab language="bash" %}
curl --request GET \
 --header "X-Api-Key: 689bbce8acc68b7a4346acca6a028e6f8126eb792b19a334f8e3f2a12ca8f561"
 --url https://api.developerhub.io/api/v1/search?query=best%20practices&version_slug=v1.0
{% /tab %}
{% /code %}

## Multi-Project Search

See [Enterprise Search](/support-center/enterprise-search) for more information about multi-project search.

## Javascript Hook for Search

If you would like to send search analytics to third-party services, you can utilize the `onsearch` JavaScript event to manage all search operations effectively. For further details, please refer to [On Search event](/support-center/developer-tools#on-search).