+++
author = "Thanni"
title = "Shopify Liquid ⭐️"
date = "2023-11-23"
description = "A beginner's guide to Shopify liquid"
tags = [
    "Shopify",
]
categories = [
    "eCommerce",
]
series = ["CRO Development"]
+++

Unlock the full potential of a Shopify store with Liquid development. This tutorial series is liquid at a glance, and not a replacement for the official documentation.

<!--more-->

NB: This note is taken from the [Shopify Liquid Documentation](https://shopify.dev/docs/api/liquid)

## <mark>Basics</mark>

```
{{ }}
```

Double curly brace delimiters denote an output.

```
{% %}
```

Curly brace percentage delimiters denote logic and control flow.

```
{{ | }}
```

Filters are placed within an output tag and denoted by a pipe character.

## Object Handles

```
{{ product.title | handle }}
```

### Referencing Handles

```
{{ pages['about-us'].url }}
```

## Operators

| ==       | equals                                  |
| -------- | --------------------------------------- |
| !=       | does not equal                          |
| >        | greater than                            |
| <        | less than                               |
| >=       | greater than or equal to                |
| <=       | less than or equal to                   |
| or       | Condition A or Condition B              |
| and      | Condition A and Condition B             |
| contains | Checks for strings in strings or arrays |

```
{% if product.tags contains 'high' %}
	Check other cheap products
{% endif %}
```

## Conditionals

```
{% if product.type == 'Love' %}
  This is a love potion!
{% elsif product.type == 'Health' %}
  This is a health potion!
{% endif %}
```

Including `else`

```
{% if product.available %}
  This product is available!
{% else %}
  This product is sold out!
{% endif %}
```

Using `unless` if the condition is true

```
{% if product.available %}
  This product is available!
{% else %}
  This product is sold out!
{% endif %}
```

Using `case`

```
{% case variable %}
  {% when first_value %}
    first_expression
  {% when second_value %}
    second_expression
  {% else %}
    third_expression
{% endcase %}
```

## <mark>Tags</mark>

## HTML Tags

```
{% form 'form_type' %}
  content
{% endform %}
```

## Iteration Tags

```
{% for product in collection.products -%}
  {{ product.title }}
{%- endfor %}
```

## Syntax Tags

```
{% comment %}
  content
{% endcomment %}
```

```
{% # content %}
```

```
{% raw %}
  expression
{% endraw %}
```

## Theme Tags

```
{% javascript %}
  javascript_code
{% endjavascript %}
```

```
{% stylesheet %}
  css_styles
{% endstylesheet %}
```

## <mark>Filters</mark>

Usage - `{{ product.title | upcase }}`

With parameters - `{{ product.title | remove: 'Health' }}`

Multiples - `{{ product.title | upcase | remove: 'HEALTH' }}`

Concat - `array | concat: array`

Map - `array | map: string`

_Check documentation for more_

## Cart Filters

`cart | item_count_for_variant: {variant_id}`

## Color Filters

`string | brightness_difference: string`

## Customer filters

`string | customer_login_link`

`{{ 'Create an account' | customer_register_link }}`

## Default filters

`{{ product.selected_variant.url | default: product.url }}`

## Font filters

`{{ settings.type_header_font | font_face }}`

## Other types of filters

- Collection
- Format (date, unit)
- HTML
- Hosted file
- Localization
- Math
- Media
- Metafield
- Money
- Payment
- String
- Tag

## <mark>Objects</mark>

### Usage

Objects, along with their properties, are wrapped in curly brace delimiters `{{ }}`

`{{ product.title }}`

```
{% assign article = articles['potion-notions/new-potions-for-spring'] %}
{{ article.title | link_to: article.url }}
```

Learn More - [Shopify Documentation](https://shopify.dev/docs/api/liquid/objects)
