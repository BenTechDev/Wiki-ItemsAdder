# 👌 权限

*   玩家

    * /ia
      * `ia.user.ia`
    * /iarecipe
      * `ia.user.iarecipe`
    * /iatexture (强行给自己安资源包)
      * `ia.user.iatexture`
    * /iatexture all (强行给每个玩家安资源包)
      * `ia.user.iatexture.all`
    * 使用物品合成配方
      * `ia.user.recipe.PERMISSION` (如果需要全部物品的权限,你可以使用这个 `ia.user.recipe.*`)
      * 关于权限的更多信息,请[查阅此处](../adding-content/item-properties/basic/item-permission.md)
    * 使用 `/ia` 物品显示
      * `ia.user.ia.seeitem.PERMISSION` (若你需要给予全部物品的权限,你可以考虑这个 `ia.user.ia.seeitem.*`)
      * 关于更多物品的权限,请[查阅此处](../adding-content/item-properties/basic/item-permission.md)
      * `ia.user.ia.search` 可以查询 `/ia` 中的物品
      * 可按类别来给予权限,详细查阅[/ia GUI ](../ia.md)
    * 表情 (font图像)
      * **/iaimage /emoji, /iaemoji, /e** Gui (可显示出带有所有"表情/font"的书)
        * `ia.user.image.gui`
      * **/iaimage** **/emoji \<text>, /iaemoji \<text>, /e \<text>** (可根据搜索显示出带有表情的列表)
        * `ia.user.image.hints`
      * 使用 **表情** 在 **聊天栏** 中
        * `ia.user.image.chat`
      * 使用 **表情** 在 **指令** 中
        * `ia.user.image.command`
      * 使用 **表情** 在 **提示牌** 中
        * `ia.user.image.sign`
      * 使用 **表情** 在 **书** 中
        * `ia.user.image.book`
      * 使用 **emojis** 在 **铁砧** 重命名栏
        * `ia.user.image.anvil`
      * 使用 **表情**
        * `ia.user.image.use.<font image name>`
        * 栗子: `ia.user.image.use.heart`
      * 使用 **text-effects** 在 **聊天栏** 中
        * `ia.user.text_effect.chat`
      * 使用 **text-effects** 在 **提示牌** 中
        * `ia.user.text_effect.sign`
      * 使用 **text-effects** 在 **书** 中
        * `ia.user.text_effect.book`
      * 使用 **text-effects** 在 **铁砧** 重命名栏
        * `ia.user.text_effect.anvil`
      * 使用 **text-effect**
        * `ia.user.text_effect.use.<effect>`
        * 栗子 ([此为列表](../text-effects-1.17+.md)):
          * `ia.user.text_effect.use.r`
          * `ia.user.text_effect.use.rw`
    * 动作表情 ([<mark style="color:blue;">玩家动作表情</mark>](../adding-content/player-emotes/))
      * 使用动作表情指令的权限: `ia.user.iaemote`
      * 使用动作表情: `ia.user.iaemote.use.<emote>`
      * 栗子:
        * `ia.user.iaemote.use.yes`
        * `ia.user.iaemote.use.*`

    ​
* 管理员
  * /iaget
    * `ia.admin.iaget`
  * /iagive
    * `ia.admin.iagive`
  * /iadrop
    * `ia.admin.iadrop`
  * /iaremove
    * `ia.admin.iaremove`
  * /iatag
    * `ia.admin.iatag`
  * /iacustommodeldata
    * `ia.admin.custommodeldata`
  * /iareload
    * `ia.admin.iareload`
  * /iazip
    * `ia.admin.iazip`
  * /iablock _(获得你正在查看的方块信息）_
    * `ia.admin.iablock`
  * /ialiquid _(获得你正在查看的液体信息)_
    * `ia.admin.ialiquid`
  * /iadurability
    * ia.admin.iadurability
  * 修改权限 (修改/ia中的按钮)
    * `ia.admin.edit`
  * /iaplayerstat write _(修改玩家的Ia数据)_
    * `ia.admin.iaplayerstat.write`
  * /iaplayerstat read _(读取玩家Ia数据)_
    * `ia.admin.iaplayerstat.read`
  * /iainfo (获得Ia相关消息)
    * `ia.admin.iainfo`
  * /iakill \<mob|all> (杀死Ia怪物)
    * `ia.admin.iakill`
  * /iasummon \<mob> \[amount]
    * `ia.admin.iasummon`
  * /iaexport \<namespace>
    * `ia.admin.iaexport`
  * /iaspawntree \<tree>
    * `ia.admin.iaspawntree`
  * /iaplaytotemanimation \<totem> \<player>
    * `ia.admin.iatotemanimation`
  * /iaplaysound \<sound> \<player>
    * `ia.admin.iaplaysound`
  * /iacleancache
    * `ia.admin.iacleancache`
  * /iahitbox (显示家具的hitbox)
    * `ia.admin.iahitbox`
  * [/iaconfig](../commands/iaconfig.md)
    * ia.admin.iaconfig
* 其他：
  * 绕过不安材质踢出的权限
    * `ia.resourcepack.bypasskick`
  * 绕过玩家放置方块不能掉落
    * `ia.admin.bypassblockplaceloot`

{% hint style="warning" %}
你 **可能需要** 使用像 [LuckPerms](https://luckperms.net/download) 可以支持后缀为 `.*` 的权限\
因为Bukkit在默认情况下并不会支持.
{% endhint %}

## Worlguard flags

{% content-ref url="../../compatibility-with-other-plugins/compatible/worldguard-flags.md" %}
[worldguard-flags.md](../../compatibility-with-other-plugins/compatible/worldguard-flags.md)
{% endcontent-ref %}
