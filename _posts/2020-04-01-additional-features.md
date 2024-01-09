---
title: Additional Features
last_modified_at: 2024-01-09 15:19:09 -0500
tags:
  - Sample Page
category: Settings
katex: true
---

<p class="message">
  This is an additional post to show other tags that is supported with this
  theme.
</p>

<!-- more -->

## Figures

<figure>
  <img src="https://via.placeholder.com/800x400" alt="Large example image">
  <figcaption>Caption describing this large image.</figcaption>
</figure>

<figure>
  <img src="https://via.placeholder.com/400x200" alt="Medium example image">
  <figcaption>Caption describing this medium image.</figcaption>
</figure>

<figure>
  <img src="https://via.placeholder.com/200x200" alt="Small example image">
  <figcaption>Caption describing this small image.</figcaption>
</figure>

## External Links and Assets

A link to [Wikipedia](https://en.wikipedia.org) which will not open in a new
window.

A link to <a href="https://en.wikipedia.org" class="external">Wikipedia</a>
which will open in a new window.

With the [Jekyll Asset Path Plugin][1] you can now organize and add links to
assets from other posts using the `asset_path` tag.

---

## Messages With Icons

This theme uses [Octicons](https://primer.style/foundations/icons/) for some of
its icons and they can be combined with [Primer colors][2] to create additional
messages with different importance.

<p class="message notice">
  <span class="message-title">{% octicon info height:24 %} Note</span>
  <br>
  Highlights information that users should take into account, even when
  skimming.
</p>

<p class="message tip">
  <span class="message-title">{% octicon light-bulb height:24 %} Tip</span>
  <br>
  Optional information to help a user be more successful.
</p>

<p class="message important">
  <span class="message-title">{% octicon report height:24 %} Important</span>
  <br>
  Crucial information necessary for users to succeed.
</p>

<p class="message warning">
  <span class="message-title">{% octicon alert height:24 %} Warning</span>
  <br>
  Critical content demanding immediate user attention due to potential
  risks.
</p>

<p class="message caution">
  <span class="message-title">{% octicon stop height:24 %} Caution</span>
  <br>
  Negative potential consequences of an action.
</p>

## Syntax Highlighting Continued

Starting with Jekyll 4.4.0 now you can mark code by adding
`mark_lines="line numbers separated by spaces"` to Rouge tags.

{% highlight js mark_lines="5 8" %}
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those
// arguments
const adder = (a, b) => a + b

// Call the function
adder(2, 6)
// > 8
{% endhighlight %}

Diff/Patch highlighting example.

<!-- markdownlint-disable MD004 MD032 -->
{% highlight diff linenos %}
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those
// arguments
- const add = (a, b) => a + b
+ const adder = (a, b) => a + b

// Call the function
adder(2, 6)
// > 8
{% endhighlight %}
<!-- markdownlint-enable -->

## Math Support

[KaTeX](https://katex.org/) is included with this theme. Now you can write math
with `$$` by adding `katex: true` in the document's front matter.

$$
\frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

$$
e^{i \theta} = \cos{\theta} + i\sin{\theta}
$$

$$
\lim_{h \to 0}{\frac{f(x+h) - f(x)}{h}} = \frac{d}{dx}f(x)
$$

[1]: https://github.com/samrayner/jekyll-asset-path-plugin
[2]: https://github.com/primer/primitives
