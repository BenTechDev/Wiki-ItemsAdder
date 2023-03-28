---
description: ItemsAdder after 3.2.0
---

# 🗑 Latest ItemsAdder

## 🗑 ItemsAdder newer than 3.3.0

### How can I remove all the items and default stuff?

{% hint style="info" %}
If you only want to make your own items, blocks and other things it's easy!\
Follow this tutorial.
{% endhint %}

#### How to delete

Open `plugins/ItemsAdder/contents/` folder and delete the folders/files you don't need

#### Finalizing the changes

Run this command: `/iacleancache items`\
Then run `/iazip`.

## 🗑 ItemsAdder older than 3.3.0

### How can I remove all the items and default stuff?

{% hint style="info" %}
If you only want to make your own items, blocks and other things it's easy!\
Follow this tutorial.
{% endhint %}

#### Deleting configurations

Open `plugins/ItemsAdder/data/items_packs/` folder and delete the folders/files you don't need

#### Deleting models, textures and other assets

Open `plugins/ItemsAdder/data/resource_pack/assets/` folder and delete the folders/files you don't need.

#### Finalizing the changes

Run this command: `/iacleancache items`

Delete these folders:

* `ItemsAdder\storage\cache\tmp\`
* `ItemsAdder\data\resource_pack\assets\minecraft\models\item\`
* `ItemsAdder\data\resource_pack\assets\minecraft\blockstates\`

Then run `/iazip`
