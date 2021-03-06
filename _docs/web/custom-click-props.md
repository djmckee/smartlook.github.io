---
title: "Custom click props"
subtitle: "Log your own specific data for click tracking."
description: ""
---

## What props can you add

The `data-recording-click-props` attribute can be added to any HTML element. When a click occurs on an element, the DOM tree is traversed from said element up to the body element and content of each of the attributes is merged into a single object.

The content of `data-recording-click-props` attribute is expected to be a JSON object.

```html
<div data-recording-click-props='{"key1":"val1","key2":42,"key3":true}'>
    <a data-recording-click-props='{"key4":"val4"}'>
        Link
    </a>
</div>
```

{: .alert .alert-warning }
Pay attention on the format of the single and double quotes. Other format of quotes is not supported.

When the link is clicked, the click properties will contain values from the attributes in addition to other values like the ones from identify API.

```json
{
   "key1": "val1",
   "key2": 42,
   "key3": true,
   "key4": "val4"
}
```