---
title: "Test"
description: ""
layout: test
---

Testing (in template)
`{{ .Content | .RenderString }}`
instead of (in shortcode)
`{{ .Inner | markdownify }}`

file: `content/test.md`
template: `layouts/page/test.html`
shortcode: `layouts/shortcodes/home-box.html`

{{< home-box "Homebox" >}}
- first `li` is wrapped in `<p>`, why?
  - with elements
  - elements
- last `li` also, and a `</div>` is added in source code
{{< /home-box >}}

<br>

The same behavior occurs when using `%` shortcode delimiters
instead of `{{ .Content | .RenderString }}`.

---

<br>

Then a test while removing indentations in the shortcode.
shortcode: `layouts/shortcodes/home-box-test.html`

{{< home-box-test "Homebox" >}}
- this time it is ok
  - no messing with `li`, `p` or `div`
  - elements
- lists work as intended
{{< /home-box-test >}}
