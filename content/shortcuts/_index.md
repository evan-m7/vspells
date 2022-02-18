---
title: "Shortcuts"
date: 2022-02-18T01:05:47-06:00

---

My Custom Description

1. Square 1

2. Square 2

Shortcodes Features:

{{< alert style="info" >}} [I’m an info alert] {{< /alert >}}
{{< alert style="danger" >}} [I’m an danger alert] {{< /alert >}}
{{< alert style="warning" >}} [I’m an warning alert] {{< /alert >}}
{{< alert style="success" >}} [I’m an success alert] {{< /alert >}}

{{< button style="primary" link="https://google.com" >}} [Button to Google] {{< /button >}}

{{< childpages >}}

{{< code lang="html" >}}
<div class="mydiv bg-primary shadow text-white">
	<h1 class="title">Hi there</h1>
	<p class="lead">I'm inside a code shortcode. Check out my syntax highlighting!.</p>
</div>
{{< /code >}}

{{< collapse title="Click so show content" >}} [Hi there, I'm the hidden content. Didn't see that one coming, huh?] {{< /collapse >}}

The doublecode shortcode works the same as the code shortcode, but extends the functionality by also rendering the code in the page. This is useful for showing the code of HTML elements in your page.

{{< doublecode lang="html" >}} 
<div class="mydiv bg-primary shadow text-white p-3 m-4 border-primary">
	<p class="h4 title">Hi there</p>
	<p class="lead mb-0">I'm inside a doublecode shortcode, that's why I look so fancy.</p>
</div>
{{< /doublecode >}}

{{< lead >}} Great for introductions or summaries. I’m a lead paragraph. That means I’m more important. And you can see that. {{< /lead >}}

{{< panel title="I'm Important" style="secondary" >}} Be sure to read me {{< /panel >}}


{{< table style="table-striped" >}}
| Tables        | are           | cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
{{< /table >}}