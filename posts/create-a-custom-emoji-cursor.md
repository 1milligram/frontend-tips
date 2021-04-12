---
title: Create a custom emoji cursor
category: trick
date: 2021-04-12 12:26:00 +7
tags:
  - posts
layout: layouts/post.njk
topics: CSS
---

There are two popular ways to create a custom cursor:

* Using an image
* Creating a canvas element and generate the base 64 image

Both approaches finally change the cursor by setting the image's URL to the `cursor` property:

```css
.custom-cursor {
    cursor: url(/path/to/image.png), auto;
}

/* Or */
.custom-cursor {
    cursor: url('data:image/png;base64,...'), auto;
}
```

To create a custom emoji cursor, we can use an inline SVG element which displays the emoji at the center as following:

```css
.custom-cursor {
    cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewport="0 0 48 48" style="fill:black;font-size:24px"><text y="50%">🚀</text></svg>') 16 0, auto;
}
```

_Demo_

<style>
.demo__cursor {
    /* Custom cursor */
    cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewport="0 0 48 48" style="fill:black;font-size:24px"><text y="50%">🚀</text></svg>') 16 0, auto;
    /* Center the content */
    align-items: center;
    display: flex;
    justify-content: center;
    /* Size */
    height: 16rem;
    width: 16rem;
    /* Misc */
    border: 1px solid rgba(0, 0, 0, .2);
}
</style>

<div class="demo__cursor">
    Let's fly!
</div>