---
layout: post
title: "Post: Video (YouTube)"
excerpt: Ceci est un résumé. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus semper turpis lectus, at porttitor magna aliquam et. Nunc vitae laoreet ligula. Vestibulum pulvinar vehicula elit, interdum luctus augue consequat id. Sed pulvinar feugiat dui sed tincidunt. Phasellus a mauris a nisl sagittis tincidunt et sollicitudin enim. Nullam enim sem, mattis sit amet laoreet sit amet, molestie sed sem.
categories:
  - Post Formats
tags:
  - Post Formats
last_modified_at: 2017-03-23T15:33:37-04:00
---

<div class="embed-responsive embed-responsive-16by9">
  <iframe width="640" height="360" src="https://www.youtube-nocookie.com/embed/l2Of1-d5E5o?controls=0&amp;" frameborder="0" allowfullscreen></iframe>
</div>

This post tests YouTube video embeds.

Simply wrap embeds with a `<div>` element and the appropriate classes:

```html
<!-- 16:9 aspect ratio -->
<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!-- 4:3 aspect ratio -->
<div class="embed-responsive embed-responsive-4by3">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!-- responsive iframe. The framesize reduces proportionately when viewing in mobile -->
<div class="video-container">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>
```
