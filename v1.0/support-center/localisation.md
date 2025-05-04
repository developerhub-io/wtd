---
type: page
title: Localisation
listed: true
slug: localisation
description: 
index_title: Localisation
hidden: 
keywords: 
tags: 
---

%product% provides localization for your documentation in two ways:

- Using an automated third party service, such as [Localize](localizejs.com).
- By using different documentation for different languages.

## Localise using Localize

Localize helps you quickly translate websites and applications into new languages and makes your translation process more efficient.

To use Localize with %product%, set up a script using [Custom HEAD Tags](/support-center/custom-javascript) like this:

{% code %}
{% tab language="html" %}
<script>
  (function(d, script) {
      script = d.createElement('script');
      script.type = 'text/javascript';
      script.async = true;
      script.onload = function(){
          !function(a){if(!a.Localize){a.Localize={};for(var e=["translate","untranslate","phrase","initialize","translatePage","setLanguage","getLanguage","detectLanguage","getAvailableLanguages","untranslatePage","bootstrap","prefetch","on","off","hideWidget","showWidget","getSourceLanguage"],t=0;t<e.length;t++)a.Localize[e[t]]=function(){}}}(window);

          Localize.initialize({
            key: 'YOUR_PROJECT_KEY',
            rememberLanguage: true,
            saveNewPhrasesFromSource: true
            // other options go here, separated by commas
          });
      };
      script.src = 'https://global.localizecdn.com/localize.js';
      d.getElementsByTagName('head')[0].appendChild(script);
  }(document));
</script>
{% /tab %}
{% /code %}

The two options `rememberLanguage` and `saveNewPhrasesFromSource` are recommended by Localize.

{% callout type="info" title="Info" %}
We manage variables in your documents as specified by Localize.
{% /callout %}

## Localise using different documentation

To localise using different documentation, you need to [create documentation](/support-center/managing-documentation#creating-documentations) for each language.

In your v1.0 version, you can have these documentation sections: `en`, `de`, and `es`. If you already have documentation for `Android SDK`, `iOS SDK`, etc., you can expand it to `Android SDK (EN)`, `Android SDK (DE)`, and `Android SDK (ES)`, and so on.

You can customize the UI text to better suit your needs. For detailed instructions, please refer to [UI translation](/support-center/ui-translation).

## Which localisation method should I choose?

It depends on how complex your documents and resources are.

If your docs are small enough and you can manage updates in one language and translate it into others, you can use different documentation for each language.

If your docs are large and you want an easy solution, consider using Localize or another third-party service. This makes it simpler to keep all parts of your documentation up to date in different languages. When you add or change content, you'll be asked to approve the new translations, ensuring your docs stay in sync. Plus, you won’t need to change your project structure.