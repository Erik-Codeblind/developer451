---
title: "Detect Dark Mode Preference"
date: 2020-12-23T11:43:38-05:00
tags: ["CSS", "Media Queries"]
summary: "Detect dark mode preference with `prefers-color-scheme` media query."
---

Detect dark mode preference with [`prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme) media query.

{{<rawhtml>}}
<style>
    @media (prefers-color-scheme: dark) {
        .light-mode-demo {
            display: none;
        }
    }
    @media (prefers-color-scheme: light) {
        .dark-mode-demo {
            display: none;
        }
    }
    .mode-detection-demo {
        font-size: 1.5rem;
        color: lightgoldenrodyellow;
        text-align: center;
        background: black;
        padding: 10px;
        margin: 1.25rem auto;
    }
</style>
<div class="mode-detection-demo">You prefer <strong class="dark-mode-demo">dark</strong><strong class="light-mode-demo">light</strong> mode!</div>

{{</rawhtml>}}

```html
    <style>
        @media (prefers-color-scheme: dark) {
            .light-mode-demo {
                display: none;
            }
        }
        @media (prefers-color-scheme: light) {
            .dark-mode-demo {
                display: none;
            }
        }
    </style>
    <p>You prefer <strong class="dark-mode-demo">dark</strong><strong class="light-mode-demo">light</strong> mode!</p>
```

