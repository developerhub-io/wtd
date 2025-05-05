---
type: page
title: Custom HTML
listed: true
slug: custom-html
description: 
index_title: Custom HTML
hidden: 
keywords: 
tags: 
---

The Custom HTML block enables you to seamlessly incorporate any web content directly into your documentation pages. This flexibility allows you to enhance your documentation with diverse elements, making it more engaging and informative for your audience.

To create a Custom HTML block:-

{% synced id="open-block-menu" %}
{% /synced %}

- Select Custom HTML {% icon classes="fas fa-window-maximize" /%}
- Type the HTML. See [How to use Custom HTML?](/support-center/custom-html#how-to-use-custom-html)
- Click on Apply.

{% callout type="warning" title="Injection Warning" %}
Never inject code that you did not inspect yourself.
{% /callout %}

## What's Included?

We already have Bootstrap 4.1 and FontAwesome 5 Free loaded which you can use.

## How to use Custom HTML?

With Custom HTML, there are two modes available:

- When the HTML content is straightforward, it is rendered directly within the page's body, eliminating the need for an iFrame. Below is an example of simple HTML code:

{% code %}
{% tab language="html" %}
<span>This is simple HTML</span>
<select style="background: red">
  <option value="0">0</option>
  <option value="0">1</option>
</select>
{% /tab %}
{% /code %}

For this mode, you can utilize inline styling effectively. Please refrain from adding any `<body>` or `<html>` tags, as the content is already rendered within a `<body>` tag. If you would like to style the elements, you can use [Custom CSS](/support-center/custom-css) to create new classes that can be applied to the elements in this section.

## iFrame in Custom HTML

For enhanced security, any HTML that contains scripts, styles, head tags, or additional iFrames will be rendered within an iFrame embedded in the page. This ensures that potentially harmful content is isolated and does not interfere with the main page. For instance, the following code would be rendered within an iFrame:

{% code %}
{% tab language="html" %}
<style type="text/css">
  .example-css {
    color: blue;
  }
</style>
<div class="example-css">
  This is HTML that will get encapsulated in an iFrame
  <button onclick="submit()"></button>
</div>
<script>
  function submit() {
    console.log("Script tags cause HTML to get encapsulated in an iFrame");
  }
</script>
{% /tab %}
{% /code %}

When using an iFrame, it is important to note that no pre-existing CSS will load. This includes styles from [auto$](/support-center/custom-css) or any third-party libraries. Therefore, you'll need to apply your own CSS rules to ensure your iFrame content appears as desired.

## Resizing Dynamic iFrames

If your Custom HTML is being embedded within an iFrame, and the iFrame dynamically adds elements to the body, this can lead to limitations in height and the appearance of scrollbars. To resolve this issue, you can instruct the iFrame to resize by using:

{% code %}
{% tab language="javascript" %}
window.postMessage('resize', '*');
{% /tab %}
{% /code %}

Use this function whenever you add elements to body dynamically.

## Custom HTML Examples

Here are our top examples:

### Fancy Button

{% html %}
<a href="https://docs.developerhub.io/?goto=wide" target="_blank" style="background-color: #d9524f; color: white; padding: 12px; border-radius: 3px; text-decoration: none !important">
    See Wide Layout
</a>
{% /html %}

Generate this button by:

{% code %}
{% tab language="markup" %}
<a href="https://docs.developerhub.io/?goto=wide" target="_blank" style="background-color: #333; color: white; padding: 12px; border-radius: 3px; text-decoration: none !important">
    See Wide Layout
</a>
{% /tab %}
{% /code %}

### Postman Collection Button

{% html %}
<a href="https://www.postman.com/run-collection/:collection_id">
	<img src="https://run.pstmn.io/button.svg" alt="Run in Postman">
</a>
{% /html %}

Generate a postman collection button by:

{% code %}
{% tab language="html" %}
<a href="https://www.postman.com/run-collection/:collection_id">
	<img src="https://run.pstmn.io/button.svg" alt="Run in Postman">
</a>
{% /tab %}
{% /code %}

### Column Layout

{% html %}
<div class="container-fluid">
  <div class="row">
    <div class="col pl-0 text-left">
      Welcome to our Supercharged documentation which has been written using DeveloperHub.io. This is a column layout.
    </div>
    <div class="col pr-0">
      <img style ="max-width: 300px" src="https://image-archive.developerhub.io/image/upload/1/bqimpvojsumftqf8hl7p/1534308910.png"/>
    </div>
  </div>
</div>
{% /html %}

Generate this column layout by:

{% code %}
{% tab language="html" %}
<div class="container-fluid">
  <div class="row">
    <div class="col pl-0 text-left">
      Welcome to our Supercharged documentation which has been written using DeveloperHub.io. This is a column layout.
    </div>
    <div class="col pr-0">
      <img style ="max-width: 300px" src="https://res.cloudinary.com/developerhub/image/upload/v1534308910/1/bqimpvojsumftqf8hl7p.png"/>
    </div>
  </div>
</div>
{% /tab %}
{% /code %}

### Grid Layout

{% html %}
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); 
            grid-template-rows: auto; gap: 14px;">
    <a href="https://docs.developerhub.io/support-center/code-blocks">
      <div style="max-width: 100%; height: 200px; background: #248FB2"></div>
    </a>
 
    <a href="https://docs.developerhub.io/support-center/images">
      <div style="max-width: 100%; height: 200px; background: #27AE44"></div>
    </a>
 
    <a href="https://docs.developerhub.io/support-center/tables">
      <div style="max-width: 100%; height: 200px; background: #EFAC4E"></div>
    </a>
 
    <a href="https://docs.developerhub.io/support-center/callouts">
      <div style="max-width: 100%; height: 200px; background: #d9524f"></div>
    </a>
</div>
{% /html %}

Generated this grid layout by:

{% code %}
{% tab language="html" %}
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); 
            grid-template-rows: auto; gap: 14px;">
    <a href="https://docs.developerhub.io/support-center/code-blocks">
      <div style="max-width: 100%; height: 200px; background: #248FB2"></div>
    </a>
 
    <a href="https://docs.developerhub.io/support-center/images">
      <div style="max-width: 100%; height: 200px; background: #27AE44"></div>
    </a>
 
    <a href="https://docs.developerhub.io/support-center/tables">
      <div style="max-width: 100%; height: 200px; background: #EFAC4E"></div>
    </a>
 
    <a href="https://docs.developerhub.io/support-center/callouts">
      <div style="max-width: 100%; height: 200px; background: #d9524f"></div>
    </a>
</div>
{% /tab %}
{% /code %}

### GitHub Gist

{% html %}
<script src="https://gist.github.com/pkuczynski/7821992.js"></script>
{% /html %}

Generated this Gist by:

{% code %}
{% tab language="markup" %}
<script src="https://gist.github.com/pkuczynski/7821992.js"></script>
{% /tab %}
{% /code %}

### PDF Reader

{% html %}
<div style="text-align: center"><iframe src="https://drive.google.com/viewerng/viewer?url=https://s3-eu-west-1.amazonaws.com/dh-misc-z/test-pdf.pdf&embedded=true" width="80%" height="390" style="border: none; left: calc(100%-150px);"></iframe></div>
{% /html %}

Generate this PDF Reader by:

{% code %}
{% tab language="markup" %}
<div style="text-align: center"><iframe src="https://drive.google.com/viewerng/viewer?url=https://s3-eu-west-1.amazonaws.com/dh-misc-z/test-pdf.pdf&embedded=true" width="80%" height="390" style="border: none; left: calc(100%-150px);"></iframe></div>
{% /tab %}
{% /code %}

### Flowcharts and Diagrams

{% html %}
<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2021-06-13T16:12:03.197Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.101 Safari/537.36\&quot; version=\&quot;14.7.7\&quot; etag=\&quot;niV-D4xH5efoW8Bwzvxj\&quot;&gt;&lt;diagram id=\&quot;nRs2ODoK7mo5jAmFDGAR\&quot; name=\&quot;Page-1\&quot;&gt;3ZZNb8IwDIZ/TY+TmoaPcdyAscsmJA47Z6lpI9KmSgOF/fqlxKUtAYnDxKZxIXkdO/ZjKxDQabZfaFakbyoGGURhvA/oLIgiQiZD+1Urh0YZEackWsSotcJKfAGKIapbEUPZO2iUkkYUfZGrPAduehrTWlX9Y2sl+7cWLAFPWHEmffVDxCZ1ajTp6K8gkhRvHhDqDJ+MbxKttjleF0R0ffw4c8aaUFhnmbJYVR2JzgM61UoZt8r2U5A124aa83u5Yj2lpyE3tzgMnMOOyS1WvgRVWAouO3NogBxrgtorDOhzlQoDq4Lx2lrZGbBaajJpd8Qu/SwwsR1oA/uOhFktQGVg9MEeQWs0QELNBIW4r9p2kIZi2mnFCDWGE5CcQrcY7AJJXKYy9Kh4PCCPn+o5szsuWVkKfiMCiHuT5wPoFDi8UF+jaZDMiF1/Xi8VjTcslbCZXOc7PuNWqq3mgF7dCToLRCb9QKfRbgIZphMwXqBjD05l39SW0f9vCx39UFsG5G5tGXttmar1GuwbEs60yDegy19/Tgg9w0Hv+Jw8eoDeVf7A/xwkOrwfJLttf+Xc0LV/Jej8Gw==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>
<script type="text/javascript" src="https://viewer.diagrams.net/js/viewer-static.min.js"></script>
{% /html %}

Generate this Flowchart by exporting from [draw.io](http://draw.io) in HTML format.

### Google Maps

{% html %}
<div class="mapouter"><div class="gmap_canvas"><iframe width="100%" height="500" id="gmap_canvas" src="https://maps.google.com/maps?q=london&t=&z=13&ie=UTF8&iwloc=&output=embed" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"></iframe><a href="https://www.pureblack.de">website erstellen lassen</a></div><style>.mapouter{text-align:center;height:500px;width:100%;}.gmap_canvas {overflow:hidden;background:none!;text-align:center;important;height:500px;width:100%;}</style></div>
{% /html %}

Generated this map by using [embedgooglemap.net](embedgooglemap.net).
