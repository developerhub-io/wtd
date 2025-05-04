---
type: page
title: Synced Blocks
listed: true
slug: synced-blocks
description: Discover how to streamline your content management with synced blocks. Learn to create, reuse, edit, and archive these blocks for consistent messaging across pages. Enhance efficiency by ensuring changes reflect everywhere instantly. Perfect for teams looking to save time!
index_title: Synced Blocks
hidden: 
keywords: 
tags: 
---

Synced blocks help you manage content effectively by allowing you to create one piece of content that can be reused on many pages. This is known as single-sourcing. When you change a synced block, those changes automatically apply to all pages using it. This keeps your content consistent and makes it easier to update, reducing duplication of work.

## Reuse Content - Creating Synced Blocks

To create a synced block:

{% synced id="open-block-menu" %}
{% /synced %}

- Choose Synced Block {% icon classes="fas fa-clone" /%}.
- Choose Create New Synced Block. A form will show.
- In the form, you need to define:
    - **ID:** An identifier for the synced block. Once saved, the ID is immutable and cannot be changed. This ID will be present in your exports, helping you keep track of your content. For instance, if you are crafting a guide on installing Docker, a suitable ID could be `docker-installation`. This ensures clarity and consistency across your documentation.
    - **Title:** Choose a title that precisely reflects the content, ensuring it is convenient for your teammates to find. Remember, the title is editable, so you can modify it at any time later.
    - **The contents:** Utilise the editor to compose the contents of the synced block. These contents are flexible and can be modified later. Feel free to include any [blocks](/support-center/blocks) that are already supported in %product%.

{% image url="https://uploads.developerhub.io/prod/8gDX/vucddld5e32itcyvza3qpqyngcbb5n48lg391wiilcya1olgev7ieq3g7mejw15h.gif" mode="responsive" height="986" width="1580" %}
{% /image %}

## Reuse a Synced Block

To reuse a synced block:

- Start a new line (using {% key key="↵" /%})
- Click on {% icon classes="fas fa-plus" /%} to open the blocks menu.
- Choose Synced Block {% icon classes="fas fa-clone" /%}.
- Choose Choose Existing Synced Block.
- Select the synced block you want to reuse, or search for it first.
- Click on Choose.

{% image url="https://uploads.developerhub.io/prod/8gDX/mvxgzhi5p6g3e8vvtrjttomzloirkk5t9ftjmu93gjt6gibsbbg8lt6zz9xtp7r6.gif" mode="responsive" height="986" width="1580" %}
{% /image %}

## Identifying a Synced Block

When you are in the editor, synced blocks will have a {% badge type="warning" text="Synced" /%} badge displayed at the top right corner. Once you hover over a synced block, an orange dotted line will appear, clearly indicating the contents contained within the synced block.

{% image url="https://uploads.developerhub.io/prod/8gDX/yqn5go6iwietc87cjzpktlc28eg6yu912ujae17haomtwy9eegs1rx22gyheo00f.jpg" mode="responsive" height="654" width="886" %}
{% /image %}

## Editing a Synced Block

When you modify a synced block, the changes are reflected in all instances where it is utilized. Please note that only Publishers have the permissions necessary to perform this operation.

To edit a synced block:

- Go to a page that has the synced block to be edited.
- Click on the {% icon classes="fas fa-pencil-alt" /%} icon at the top right of the synced block.
- A form will appear where you can modify the title and contents.
- Make the changes and click Save.

## Deleting/Archiving a Synced Block

Once a synced block is added to your project, it cannot be deleted; however, it can be archived. Archiving a synced block does not eliminate its instances from any page where it has been added. Instead, it only removes the block from the list of synced blocks available for your teammates to select.

To archive a synced block:

- Start a new line (using {% key key="↵" /%})
- Click on {% icon classes="fas fa-plus" /%} to open the blocks menu.
- Choose Synced Block {% icon classes="fas fa-clone" /%}.
- Choose Choose Existing Synced Block.
- Find the synced block to archive, and hit the {% icon classes="fas fa-times red" /%} icon next to it.
- Confirm your choice.

## Using Page Links in Synced Blocks

You can link to pages inside a synced block. Please note that there are certain limitations to its use that you should be aware of.

{% callout type="warning" title="Page Linking Limitation" %}
When the synced block is used in a different version than the one created in, it will be matched using the page slug. Changing the page slug in the source version or the destination version will break the link - and you will be notified when viewing a page that has the synced block.

For example: If you created a synced block that links to "Contact Us" page in v1.0 having "contact-us" slug, then used the synced block in v2.0 and later changed the Contact Us page slug to "how-to-contact-us", then the page link will break in v2.0. You would need to create a separate synced block for v2.0 to handle this situation.
{% /callout %}