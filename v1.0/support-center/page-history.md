---
type: page
title: Page History
listed: true
slug: page-history
description: 
index_title: Page History
hidden: 
keywords: 
tags: 
---

Supercharged plans grant users the ability to view and revert to previous versions of each page, enhancing flexibility and control over content management.

{% image url="https://uploads.developerhub.io/prod/8gDX/3nts83khtsbpql3shuyqvlp994x117zi8vlef8utd0fg50tlf89s5erzniyaelfv.png" mode="responsive" height="985" width="1751" %}
{% /image %}

## View and Revert Edit History

To view edit history of a page:

- Select the page from the index.
- Select Page Info {% icon classes="fas fa-file-alt inv-icon" /%} from the right sidebar.
- Each edit will be shown in chronological order, newest (or current) first, supplied with the team member who made the changes, the local time, and an "estimate" of how many lines have been added or removed.
- On clicking on an edit history, the page will preview the change that was made.
- You may at this stage revert to this change. This will create a new edit history.

{% callout type="info" title="Info" %}
Users upgrading to a higher tier plan will be able to access history older than what their previous plan allowed immediately.
{% /callout %}

{% callout type="success" title="Behaviour when Cloning" %}
When you clone a version, the page history of the original page will be accessible on the cloned page - even if you delete the original version.
{% /callout %}

## Annotate History

To simplify the process for your team in understanding the modifications you’ve made in the edit history, you have the option to annotate each change (similar to adding a commit message). To annotate a history:

- Select the page from the index.
- Select Page Info {% icon classes="fas fa-file-alt inv-icon" /%} from the right sidebar.
- Hover over the edit you wish to annotate, and click on the edit icon {% icon classes="fas fa-edit" /%} next to it.
- Type in your commit message and submit it.

## See Changes since Published Page

If you are currently working on a draft and need to review the changes made since the page was last published, follow the steps outlined below:

- Select the page from the index.
- Select Page Info {% icon classes="fas fa-file-alt inv-icon" /%} from the right sidebar.
- Next to Edit History, click on Compare With Published.

{% image url="https://uploads.developerhub.io/prod/8gDX/llh210trvxo0twlkzza5cm9facf0vtb8egfs8qxcbkgzabc6x2xqb8q4tzkcvtq1.png" mode="responsive" height="164" width="339" %}
{% /image %}

All edits made since the last published version will be consolidated and displayed.

## Known Limitations & Bugs

- Diffs might have extra spaces and dashes after an import.
- If a [block](/support-center/blocks) is changed, we highlight it in orange and show only the new state, without displaying the previous state.