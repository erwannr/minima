---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
---

This is patch-1

Checking [j-r-l](https://github.com/benbalter/jekyll-relative-links).

{% raw %}
```
[About]({{site.baseurl}}/about/)
```
{% endraw %}

[about.md]({{site.baseurl}}/about/) <-- OK

{% raw %}
```
[About](./about.md)
```
{% endraw %}

[about.md](./about.md) <-- ?

{% raw %}
```
[About](./about.html)
```
{% endraw %}

[about.md](./about.html) <-- ?

{% raw %}
```
[About]({{site.baseurl}}/dummy/)
```
{% endraw %}

[_pages/dummy.md]({{site.baseurl}}/dummy/) <-- 404.

{% raw %}
```
[_pages/dummy.md]({{site.baseurl}}/_pages/dummy/)
```
{% endraw %}
