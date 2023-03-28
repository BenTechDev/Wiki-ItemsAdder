---
description: /ia command menu
---

# 📃 Recipes menu

## Menu settings and "All" category

`ia_gui.yml` contains settings about the `/ia` command GUI.\
It also contains the **"all"** category which shows every ItemsAdder item.

{% hint style="info" %}
Default ItemsAdder pack categories are inside `categories.yml` files on each `namespace` folder.\
For example: `contents/iasurvival/configs/categories.yml`
{% endhint %}

## Creating a custom category

If you want to create your own category you have to create and add it to your own `.yml` file in your [namespace](broken-reference).\
<mark style="color:red;">Do not add your categories into the</mark> <mark style="color:red;"></mark><mark style="color:red;">`ia_gui.yml`</mark> <mark style="color:red;"></mark><mark style="color:red;">file!</mark>\
This is an example:

```yaml
info:
  namespace: my_items
categories:
  swords:
    enabled: true
    icon: "my_items:custom_item"
    name: 'Swords'
    permission: "ia.menu.swords"
    # THIS IS OPTIONAL. Plugin will take the one in ia_gui.yml if not set.
    font_image:
      name: "mcguis:blank_menu"
      x_position_pixels: -16
    # THIS IS OPTIONAL. Plugin will take the one in ia_gui.yml if not set.
    title_position_pixels: 0
    items:
      - "my_items:custom_item"
      - "my_items:custom_item_2"
      - "my_items:custom_item_3"
```

Remember to give your users permission for each category if you want them to see the categories.\
This example category permission is: `ia.menu.seecategory.swords`

{% hint style="info" %}
**`font_image` and `title_position_pixels` are optional.**\
Plugin will take the one in `ia_gui.yml` if not set.

This option is good if you want to have a different background for each category.
{% endhint %}

{% hint style="success" %}
**Categories** with the **same name** and different namespace **will be merged**, this is **helpful** if you have two "swords" categories.\
This allows you to open **`/ia`** menu and see all swords organized in the same category instead of having 2 swords categories.
{% endhint %}
