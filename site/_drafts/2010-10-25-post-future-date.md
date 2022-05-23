---
layout: post
title: "Post: Future Date"
excerpt: Ceci est un résumé. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus semper turpis lectus, at porttitor magna aliquam et. Nunc vitae laoreet ligula. Vestibulum pulvinar vehicula elit, interdum luctus augue consequat id. Sed pulvinar feugiat dui sed tincidunt. Phasellus a mauris a nisl sagittis tincidunt et sollicitudin enim. Nullam enim sem, mattis sit amet laoreet sit amet, molestie sed sem.
date: 9999-12-31
categories:
  - Post
last_modified_at: 2017-03-09T12:45:25-05:00
---

This post lives in the future and is dated {{ page.date | date: "%c" }}. It should only appear when Jekyll builds your project with the `--future` flag.

```bash
jekyll build --future
```