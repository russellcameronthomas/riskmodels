---
layout: default
title: "Table of Contents"

---
<style type="text/css">
ol li {
text-align:left
list-style-type: upper-roman
}
ol li ol li {
text-align:left
list-style-type: decimal;
}
</style>

{% assign sorted_pages = site.financial | sort:"name" %}

<div class = "author-block">
<a href="{{ site.author_url }}" target="_blank" style="font-weight: bold;font-size:120%;">{{ site.author }}</a><br>
{{ site.author_title }}<br>
{{ site.author_affiliation }}<br>
</div>

{% for p in sorted_pages %}
    {% if p.hidden %}
    {% else %}
        {% if p.layout == 'chapter' %}
            {% if p.is_section %}
                {% if p.status == 'stub' %}
1. **{{ p.title }}**<br>{% else %}
1. **<a class="chapter-link" href="{{ site.baseurl }}{{ p.url }}" target="_blank">{{ p.title }}</a>**<br>{% endif %}
        <em>{{ p.description }}</em>
            {% else %}
                {% if p.status == 'stub' %}
    1. **{{ p.title }}**<br>{% else %}
    1. **<a class="chapter-link" href="{{ site.baseurl }}{{ p.url }}" target="_blank">{{ p.title }}</a>**<br>{% endif %}
            <em>{{ p.description }}</em>        
            {% endif %}
        {% endif %}
    {% endif %}
{% endfor %}

### Other Resources

A. <a href="{{ site.baseurl }}/editor.html" target="_blank">Interactive WebPPL editor</a> -- to create and modify your own markdown pages, saved in your browser's cache.

B. <a href="https://probmods.org/v2/" target="_blank"><em>Probabilistic Models of Cognition</em></a> -- an on-line book for the cognitive science applications of WebPPL. *CAUTION*: This book uses an older version of WebPPL and the syntax and functions are somewhat different than used in this tutorial.

C.  <a href="http://dippl.org/chapters/02-webppl.html" target="_blank">WebPPL Language Manual</a> -- a tutorial introduction to the design of WebPPL, which can help you understand how the language is interpreted and executed, and therefore why the language is designed the way it is (e.g. functional programming).

D.  <a href="http://docs.webppl.org/en/master/" target="_blank">WebPPL Language Reference</a> -- specification of components and functions in the language.

E.  <a href="http://webppl.org" target="_blank">WebPPL.org</a> -- interactive editor and local installation instructions. (Note: this editor does not have all the javascript libraries necessary to run the models presented here.)