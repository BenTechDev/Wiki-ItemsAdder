# 🔋 HUDs

In order to create custom HUDs you have 2 examples provided in ItemsAdder and they make use of every feature available.

These two HUDs are the mana bar and the thirst bar.\
You can find them in the **realcraft** and in the **magiccraft** namespaces.

![](<../../../.gitbook/assets/image (23).png>)

## Disable/enable huds in worlds

You can easily disable/enable huds in some worlds, here some examples:

### Enable in all worlds

To enable them in all worlds you just have to avoid entering any world in the list, don't write the property at all.

```yaml
huds:
  thirst_bar:
    enabled: true
```

### Enable in all worlds but not in `world_the_end`

```yaml
huds:
  thirst_bar:
    enabled: true
    worlds:
    - "!world_the_end"
```

Notice the `!` in front of the world name. (It's very important to use the `" "` characters or plugin won't work (`.yml` bug).

### Enable in all worlds of name which starts with `world_` or `adventure`

```yaml
huds:
  thirst_bar:
    enabled: true
    worlds:
    - "world_*
    - "adventure*
```

Notice the `*` at the end, this means "_**any**_". (keep in mind that this works only at the end of the name)
