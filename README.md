# 500 Lines
A super great resource at: http://www.aosabook.org/en/500L/introduction.html
## -1- A Template Engine

### I. Main idea: similar to Python string's **format method** like " A is {title} of B".format(title="father"); Whereas, **template engine** is also a formatter, but much more powerful.
> An important phase in any web application is generating HTML to be served to the browser.

> Very few HTML pages are completely static: they involve at least a small amount of __dynamic data__, such as the user's name. Usually, they contain a great deal of dynamic data: product listings, friends' news updates, and so on.

> The mostly-static style used in templates is the opposite of how most programming languages work.

> A template language flips this around: **the template file is mostly static literal text, with special notation to indicate the executable dynamic parts.**

### II. template syntax
1.  dot : {{product.price}}
```html
...<p>The price is: {{product.price}}, with a {{product.discount}}% discount.</p>
```
2. filters with pipe character:  {{story.subject|slugify|lower}}
```html
<p>Short name: {{story.subject|slugify|lower}}</p>
```
3. logic control: {% if user.is_logged_in %}  {% for product in product_list %}
```html
<p>Products:</p>
<ul>
{% for product in product_list %}
    <li>{{ product.name }}: {{ product.price|format_price }}</li>
{% endfor %}
</ul>
```
4. comment: {# This is the best template ever! #}
```html
{# This is the best template ever! #}
```
### III. Two approach to implement the Template Engine
1. Two main phases: **parsing the template**, and then **rendering the template**

2. For 'parsing phase':
- interpretation (Django )
- compilation (Jinja2 and Mako | also, we will use)


### IV. Compiling to Python
1. The template engine will compile templates to Python method called **"render_function(context, do_dots)"**
2. context dictionary : carry kinds of dynamic variables to be embedded in template
3. do_dots method: passed-in method name, handling dot access
