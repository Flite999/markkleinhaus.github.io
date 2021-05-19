---
layout: post
title:  "Using Math/Logic Symbols in Markdown for Jekyll"
date:   2021-05-19
categories: mathematics
---

There is a myriad of approaches to this out on the internet - here's what worked for me.

1. Run `bundle info minima` in terminal.
2. Copy the `Path` value and open that directory.
3. Copy the `default.html` file under `_layouts` folder in that directory.
4. Create a `_layouts` directory in your Jekyll blog root.
5. Paste the `default.html` file in your new `_layouts` directory.
6. Paste this line right after the `<html>` opening line: 
```<script type="text/javascript"
    src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
```
7. Save.
8. Edit your `_config.yml` file, add this line to the `# Build settings` block: 
`markdown: kramdown`
9. Run `gem install kramdown` in your terminal.
10. Finally, in your post, add `usemathjax: true` to your post variables, and enclose mathematical/logic symbols and equations with `$$` on both sides.
11. Formatting resources:
* http://davidagler.com/teaching/logic/handouts/supplemental_material/MarkdownForSymbolicLogic.html
