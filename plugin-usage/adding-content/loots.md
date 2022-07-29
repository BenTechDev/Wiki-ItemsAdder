# 🎁 战利品

Loots（战利品）可以在特定的情况下指定掉落特定物品.
可以创建的战利品类型:&#x20;

* blocks（挖掘方块）
* mobs （击杀怪物）
* fishing （钓鱼）

例如：这是我在 .yml 中创建的战利品属性

```yaml
loots:
  blocks:
    ruby_ore:
      type: itemsadder:ruby_ore
      items:
        ruby:
          item: itemsadder:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
    nether_quartz_ore:
      type: NETHER_QUARTZ_ORE
      drop_only_first: true
      items:
        crystal:
          item: itemsadder:crystal
          min_amount: 1
          max_amount: 2
          chance: 10
        knowledge_fragment:
          item: itemsadder:knowledge_fragment
          min_amount: 1
          max_amount: 2
          chance: 15
```

该示例在 **blocks** 分类中有两个战利品配置 

第一个战利品为 **ruby_ore**（你可以在任何地方对其进行调用），当你挖掘自定义方块 **itemsadder:ruby_ore** 后将会 **100%** 掉落 1-2个 **itemsadder:ruby**

第二个战利品为 **原版方块**
The second one is a loot from a vanilla **block**. As you imagine it will drop a **crystal** or a **knowledge\_fragment** when the player breaks a **NETHER\_QUARTZ\_ORE**.\
These **drops** are decided by **ItemsAdder** based on **chance** you set.&#x20;

{% hint style="info" %}
特殊属性：**drop\_only\_first**\
This allows you to **stop** the **plugin** from **dropping each** of the **items** that succeed into extracting a **correct** chance to be **dropped**. \
**WARNING**: this would make your items **harder** to be **dropped**.
{% endhint %}

## 仅在特定的生物群系中掉落

```yaml
loots:
  blocks:
    ruby_ore:
      type: itemsadder:ruby_ore
      biomes:
        - PLAINS
        - SUNFLOWER_PLAINS
        - MOUNTAINS
      items:
        ruby:
          item: itemsadder:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
```

## 忽略时运附魔效果

通过添加 **ignore\_fortune** 属性来使战利品忽略时运的附魔效果

```yaml
loots:
  blocks:
    ruby_ore:
      type: itemsadder:ruby_ore
      items:
        ruby:
          item: itemsadder:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
          ignore_fortune: true # <----- here
```

## 其他类型的战利品

除了方块掉落的战利品，还有其他类型的战利品.\
比如：击杀怪物或钓鱼. 下面是一些示例:

### 钓鱼（fishing）

```yaml
loots:
  fishing:
    loot_blue_parrotfish:
      biomes:
        - WARM_OCEAN
      items:
        item_1:
          item: itemsadder:blue_parrotfish
          min_amount: 1
          max_amount: 1
          chance: 5
    loot_green_sunfish:
      items:
        item_1:
          item: itemsadder:green_sunfish
          min_amount: 1
          max_amount: 1
          chance: 5
    loot_goldfish:
      items:
        item_1:
          item: itemsadder:goldfish
          min_amount: 1
          max_amount: 1
          chance: 5
```

### 怪物

```yaml
loots:
  mobs:
    villager:
      type: VILLAGER
      nbt:
        profession:
          path: VillagerData.profession
          value: minecraft:farmer
          type: string
      items:
        item_1:
          item: itemsadder:straw_hat
          min_amount: 1
          max_amount: 1
          chance: 100
    ender_dragon:
      type: ENDER_DRAGON
      items:
        item_1:
          item: itemsadder:ender_dragon_wings
          min_amount: 1
          max_amount: 1
          chance: 100
```

{% hint style="info" %}
### 自定义怪物掉落物 ([旧实体方法](mobs/old-method/))
{% endhint %}

为了使 Itemsadder 能在你击杀了自定义怪物（基于Itemsadder创建）后掉落指定的物品，你需要使用 `ItemsAdderMob` 属性，配置如下：

```yaml
loots:
  mobs:
    soul:
      type: HUSK
      metadata:
        ItemsAdderMob:
          name: "ItemsAdderMob"
          value: "creaturesplus:soul"
          type: "string"
      items:
        ruby:
          item: ruby
          min_amount: 1
          max_amount: 1
          chance: 100
```

在该示例中，我设置了 `ItemsAdderMob`  属性并指定了自定义怪物 **命名空间:id**
（在该示例中的自定义怪物为 `creaturesplus:soul` ）

{% hint style="info" %}
### 自定义实体战利品
{% endhint %}

为了使 Itemsadder 能在你击杀了自定义怪物（基于Itemsadder创建）后掉落指定的物品，你需要使用 `ItemsAdderEntity` 属性，配置如下：

```yaml
loots:
  mobs:
    soul:
      type: HUSK
      metadata:
        ItemsAdderEntity:
          name: "ItemsAdderEntity"
          value: "custom:ninja_skeleton"
          type: "string"
      items:
        ruby:
          item: ruby
          min_amount: 1
          max_amount: 1
          chance: 100
```

在该示例中，我设置了 `ItemsAdderEntity` 属性并指定了自定义怪物 **命名空间:id**
（在该示例中的自定义怪物为 `custom:ninja_skeleto` ）

{% hint style="info" %}
### 村民职业（以及想要匹配的任何其他 NBT 属性）
{% endhint %}

```yaml
loots:
  mobs:
    villager:
      type: VILLAGER
      nbt:
        profession:
          path: VillagerData.profession
          value: minecraft:farmer
          type: string
      items:
        item_1:
          item: itemsadder:straw_hat
          min_amount: 1
          max_amount: 1
          chance: 100
```

As you can see I set **profession** attribute and specified the **NBT attribute** path, which in this case is **VillagerData.profession**.\
Then I set value to **minecraft:farmer**, this tells ItemsAdder to match only **villagers** with attribute **VillagerData.profession** set to **minecraft:farmer**.

{% hint style="warning" %}
`nbt` 的 `type` 属性和 `metadata（对应Value）` 属性非常重要，不要忘记配置！否则将无法匹配!
{% endhint %}

{% hint style="info" %}
### 基于 Tile 实体的 NBT数据 掉落（例如 刷怪笼（Spawner））
{% endhint %}

```yaml
loots:
  blocks:
    change_me:
      enabled: true
      type: SPAWNER
      nbt:
        spawner_type:
          path: SpawnData.entity.id
          value: minecraft:zombie
          type: string
      items:
        change_me:
          item: ACACIA_BOAT
          min_amount: 1
          max_amount: 1
          chance: 100
          ignore_fortune: false
```

{% hint style="warning" %}
如果你希望能够通过使用具有 **精准采集** 的附魔物品，从刷怪笼中获取物品，请启用该选项

```yaml
loots:  
    allow-loots-drop-from-spawners-using-silk-touch: true
```
{% endhint %}
