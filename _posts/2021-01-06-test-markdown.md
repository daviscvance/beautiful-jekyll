---
layout: post
title: Markdown Template
subtitle: Useful to copy ideas from
author: Davis Vance
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
# cover-img: /assets/img/path.jpg
# thumbnail-img: /assets/img/thumb.png
# share-img: /assets/img/path.jpg
tags: [markdown, cheat_sheets]
comments: true
last-updated: 2021-03-07
---
<head>
  <script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
  <script>mermaid.initialize({startOnLoad:true});</script>
  <script type="text/javascript" async src="//cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML"></script>
  <meta charset="utf-8">
</head>

Big shoutout to [Dean Attali (daattali)](https://github.com/daattali) for making
this all this possible with
[beautiful-jekyll](https://github.com/daattali/beautiful-jekyll). This is the
start of my documentation journey.

# Single Hash Heading {#custom-id}
This is a collection of markdown for quick referencing. [^1] Markdown is useful.
It helps write `HTML code` with _simplicity_. [^footnote-42]

Unfortunately, some of these features may not work outside of GitLab. And also,
some of these features only work in the blog (mermaid and mathjax scripts in
head). You can use GitLab Flavored Markdown in the following areas:

* Comments
* Issues
* Merge requests
* Milestones
* Snippets (the snippet must be named with a .md extension)
* Wiki pages
* Markdown documents inside repositories
* Epics (ULTIMATE)

[Gitlab Example](https://gitlab.com/gitlab-org/gitlab/blob/master/doc/user/markdown.md)

[^1]: Footnote 1 is just mentioning that I started with
[md guide's cheat sheet](https://www.markdownguide.org/cheat-sheet/).

[^footnote-42]: Tehe.

---

**Embolden yourself with two asterisks and also knowledge!**

## Second heading with 2 hashes

Here's a ~~striking~~ly good table:

| Number | Color?(jk) | Other |
| :--- | :------: | ---: |
| Five | `#FF0000AA` | Hey |
| 100 | `RGB(0,255,0)` | Ho |
| Seven | `RGB(0%,100%,0%)` | Watch it |
| 999 | `RGBA(0,255,0,0.3)` | Flow |

How do you like them apples? <br> Mm yeah.

---

### Inline Media
![Do do do dodo](https://i.imgur.com/WsUV4DK.gif)

It can also be centered!

![Dun Da dun dun Da](https://i.imgur.com/WsUV4DK.gif){: .mx-auto.d-block :}

Silly video embedded
<a
  href="http://www.youtube.com/watch?feature=player_embedded&v=VOC3huqHrss"
  target="_blank">
  <img
    src="http://img.youtube.com/vi/VOC3huqHrss/0.jpg"
    alt="IMAGE ALT TEXT HERE"
    width="240"
    height="180"
    border="10"/>
</a>

### Checklist
1. [x] Just going to have to make do with what you can.
1. [ ] But know that there is a great beyond.
   * [ ] For which, you can explore.
   * [x] Uses markdown: [kramdown](https://kramdown.gettalong.org/syntax.html)
          in YAML

### Code Blocks
Highlighted code block:

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

```javascript
var foo = function(bar) {
  return(bar + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

### Boxes
> Add all sorts of stuff.
> Boxes, notifications, warnings and errors galore.

### Notification

{: .box-note}
**Note:**  Adding a note here to tell you about notes.

 - {+ Do add color +}
 - [- but be afraid -]
 - [+ of errors +]
 - {- :tongue: -}

### Warning

{: .box-warning}
**Warning:** Take your time, Hurry up! :snail:

### Error

{: .box-error}
**Error:**
Don't use these: [Emoji List](https://gist.github.com/rxaviers/7360908)

:speak_no_evil:

## Math
$$
\begin{aligned}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\
  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{aligned}
$$

## Diagrams / Flowcharts

Reference: [Mermaid documentation](https://mermaid-js.github.io/mermaid/#/)

---
Flowchart 1
<div class="mermaid">
graph TD;
    A(Alpha)-->B(Beta);
    A-->C;
    B(Beta)-->D(Delta);
    C-->D;
    style A fill:#f9f, stroke:#333, stroke-width:4px
    style B fill:#bbf, stroke:#f66, stroke-width:2px, color:#fff, stroke-dasharray: 5 5
    click A callback "Tooltip"
    click B "https://daviscvance.github.io/" "Self reference link"
    click C call callback() "Tooltip"
    click D href "http://www.github.com" "This is a different link"
</div>

Flowchart 2
<div class="mermaid">
graph TD
    A[Christmas] -->|Get money| B(Go shopping)
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
</div>

---

Gantt Chart
<div class="mermaid">
gantt
       dateFormat  YYYY-MM-DD
       title Adding GANTT diagram functionality to mermaid

       section A section
       Completed task            :done,    des1, 2021-01-06, 2021-01-08
       Active task               :active,  des2, 2021-01-09, 3d
       Future task               :         des3, after des2, 5d
       Future task2              :         des4, after des3, 5d

       section Critical tasks
       Completed task in the critical line :crit, done, 2021-01-06, 24h
       Implement parser and jison          :crit, done, after des1, 2d
       Create tests for parser             :crit, active,           3d
       Future task in critical line        :crit, 5d
       Create tests for renderer           :2d
       Add to mermaid                      :1d

       section Documentation
       Describe gantt syntax               :active, a1, after des1, 3d
       Add gantt diagram to demo page      :after a1,               20h
       Add another diagram to demo page    :doc1, after a1,         48h

       section Last section
       Describe gantt syntax               :after doc1, 3d
       Add gantt diagram to demo page      :20h
       Add another diagram to demo page    :48h
</div>

---

<div class="mermaid">
graph TB
    sq[Square shape] --> ci((Circle shape))
    sq[Square shape] --> RO2
    sq[Square shape] --> od3

    subgraph Flow1
        ODD>Odd shape]-- Two line<br/>edge comment --> RO
        DI{Diamond with <br/> line break} -.-> RO(Rounded<br>square<br>shape)
        DI==>RO2(Rounded square shape)
    end

    %% Notice that no text in shape are added here instead that is appended further down
    e --> od3>Really long text with linebreak<br>in an Odd shape]

    %% Comments after double percent signs
    e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز)

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

     classDef green fill:#9f6, stroke:#333, stroke-width:2px;
     classDef orange fill:#f96, stroke:#333, stroke-width:4px;
     class sq,e green
     class DI orange
</div>