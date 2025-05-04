---
type: page
title: Project Structure
listed: true
slug: project-structure
description: Get the most flexibility with DeveloperHub projects. Understand how projects are structured with landing pages, versions, documentation, and references. Customize branding, look, and team. Learn the best practices for versioning and organizing your docs effectively.
index_title: Project Structure
hidden: 
keywords: 
tags: 
---

%product% projects offer you the most flexibility for creating documentation.

## How Are Projects Structured?

Projects are at the top of the documentation hierarchy. Each project contains the following:

- A landing page, which users see when they first navigate to your documentation. 
- One or more version numbers, which represent different versions of your documentation. 

Each version contains:

- One or more documentation sections.
- One or more references.

Each documentation section contains:

- An index of pages, categories and external links.

Different projects, even if owned by the same team, are not inter-linked and their data is siloed. You may link between projects using external links. Each project can have its own customizations, branding, look, feel and team.

### Example Setup

A simple documentation project can have a setup similar to the following:

- **Project:** Pied Piper
    - **Version:** v1.0
        - **Documentation Section:** Docs (containing any number of pages)

A larger project could have a setup similar to the following:

- **Project:** Pied Piper
    - **Version:** v1.0
        - **Documentation Section:** Getting Started
        - **Documentation Section:** Android SDK
        - **Documentation Section:** iOS SDK
        - **Documentation Section:** Knowledge Base

    - **Version:** v2.0 (Latest)
        - **Documentation Section:** Getting Started
        - **Documentation Section:** Android SDK
        - **Documentation Section:** iOS SDK
        - **Documentation Section:** Knowledge Base

## What If I Don't Need Versions?

If your docs are not versioned you can use a generic name for the default version, such as the name of your project. Under that version, you can have all the documentation sections and API references you need. For example, User Guide, Knowledge Base, FAQ, Android SDK, iOS SDK, etc.

If you only have one version, which is the default version, then the version name will not appear in the URL according to our [URL Strategy](/support-center/previewing-documentation#url-strategy).

For example, our own docs are not versioned and we only have a `v1.0`. However, if you are on this page, then you'll notice that the link is actually `support-center/structuring-documentation` with no mention of `v1.0`.

### Example Setup

An unversioned project could have a setup similar to the following:

- **Project:** Pied Piper
    - **Version:** pied-piper
        - **Documentation section:** Getting Started
        - **Documentation section:** Android SDK
        - **Documentation section:** iOS SDK
        - **Documentation section:** Knowledge Base

Remember that you can hide the version selector using [Custom CSS](/support-center/custom-css), see [Hide Version Selector/Picker](/support-center/css-customisations#hide-version-selectorpicker).

## How Are Versions Used?

Versions act as containers for documentation sections and API references that can be cloned.

## Best Practices

To use %product% to its fullest, we recommend the following:

- It's important to use versioning correctly, as the landing page shows the contents of the default/latest version.
- If a documentation contains too many pages, you might want to separate them into different documentation sections.