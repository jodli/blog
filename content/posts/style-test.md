---
title: "Style Test"
date: 2026-03-28
unlisted: true
---

A quick test of all content elements against the new design.

## Block quote

> The bottleneck is not coding. It never was. The bottleneck is figuring out what to build, getting people to agree on it, and then finding out you were wrong anyway.

And a quote with attribution:

> "Every system is perfectly designed to get the results it gets."
>
> — W. Edwards Deming

## Code

Inline code looks like this: `hugo server --buildDrafts` and should blend with the text.

A fenced code block:

```go
func (s *Server) HandleRequest(w http.ResponseWriter, r *http.Request) {
    ctx := r.Context()
    session, err := s.store.GetSession(ctx, r.Header.Get("X-Session-ID"))
    if err != nil {
        http.Error(w, "session not found", http.StatusUnauthorized)
        return
    }

    // The interesting part: we don't process the request ourselves.
    // We hand it to the module that owns this domain.
    module := s.registry.ModuleFor(r.URL.Path)
    module.Handle(ctx, session, w, r)
}
```

And a short one:

```
Assumption → LLM makes it concrete → Human evaluates → Better decision
```

## Lists

Unordered:

- First item with some longer text that might wrap to the next line to test alignment
- Second item
- Third item

Ordered:

1. Herausfinden was das Richtige ist
2. Warten auf Entscheidungen
3. Das Falsche bauen
4. Nochmal von vorne

## Image

![A test image](/blog/images/thanks-no-time.png)

## Mixed content

Here's a paragraph with **bold text**, a [link to something](https://example.com), and some `inline code`. The paragraph should flow naturally and not feel cramped.

---

A horizontal rule above. And a final paragraph below it to test spacing.
