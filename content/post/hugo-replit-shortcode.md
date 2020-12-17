---
title: "Hugo Shortcode to Embed Repl.it Posts with Inline Frames"
date: 2020-12-16T18:51:45-05:00
summary: "Example of creating a custom Hugo shortcode to embed pages using iframes with custom attributes."
---

If you want to use `<iframe>` tags with custom attributes to embed pages into Hugo posts, one easy approach is to create a custom shortcode template. This example will demonstrate creating a custom shortcode to embed [repl.it](https://repl.it/) pages.

1. Add the following to `layouts/shortcodes/replit.html`:

```go 
<iframe height="500px" width="100%" src="{{ .Get "src" }}?lite=false" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>
```

2. Use the shortcode in a post like this:

> {{&lt;replit src="https&#58;//repl.it/@Erik_Codeblind/ReducerPattern">}}

Note the resulting shortcode name is derived from the file name, `replit.html => <replit>`. 

3. Ta-dah!

Behold the **{{&lt;replit src="">}}** shortcode in action.

{{<replit src="https://repl.it/@Erik_Codeblind/ReducerPattern">}}
