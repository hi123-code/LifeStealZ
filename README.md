![LifestealZBanner](https://strassburger.org/img/lifestealz/banner_logo.png)

---

![paper](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/supported/paper_vector.svg)
![purpur](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/supported/purpur_vector.svg)
[![github](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/available/github_vector.svg)](https://github.com/KartoffelChipss/lifestealz)
[![modrinth](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/available/modrinth_vector.svg)](https://modrinth.com/plugin/lifestealz)
[![discord-plural](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/social/discord-plural_vector.svg)](https://strassburger.org/discord)
[![gitbook](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/documentation/gitbook_vector.svg)]([https://lsz.strassburger.dev/](https://lsz.strassburger.dev/))

LifeStealZ is a lifesteal SMP plugin, that allows you to steal hearts from other players, when you kill them. If a player has no more hearts, he is eliminated. You can craft additional hearts or a revive crystal. With this crystal, you can bring back eliminated teammates.

LifeStealZ offers a great amount of admin tools and is highly customizable. You can change every message and change everything about the custom items.

<br>

---

![FeaturesBanner](https://strassburger.org/img/lifestealz/banner_features.png)
* ✅ Stealing hearts
* ✅ Withdraw hearts
* ✅ Customizable heart items
* ✅ Custom crafting recipes
* ✅ Revive item
* ✅ Maximal and starter hearts
* ✅ Disable totems
* ✅ Disable crystal pvp
* ✅ Ingame recipe viewer
* ✅ PlaceholderAPI placeholders
* ✅ Custom WorldGuard flags
* ✅ Admin commands
* ✅ HEX colors and gradients support
* ✅ SQLite and MySQL support

<br>

---

![PermissionsBanner](https://strassburger.org/img/lifestealz/banner_permissions.png)

- **lifestealz.admin.reload** - Allow to reload the plugin
- **lifestealz.admin.setlife** - Allow to set the amount of hearts, a player has
- **lifestealz.admin.giveitem** - Allow to give custom items to a player
- **lifestealz.admin.eliminate** - Allows to eliminate players with the `/eliminate` command
- **lifestealz.admin.revive** - Allow a player to revive another player with the `/revive` command
- **lifestealz.bypassrevivelimit** - Allow a player to bypass the revive limit
- **lifestealz.withdraw** - Allow a player to withdraw hearts (true by default)
- **lifestealz.revive** - Allow a player to revive others with a revive crystal (true by default)
- **lifestealz.viewrecipes** - Allow a player to view the custom recipes (true by default)
- **lifestealz.help** - Allow a player to access the help menu (true by default)
- **lifestealz.viewhearts** - Allow a player to view the amount of hearts (`/hearts``) he has (true by default)

<br>

---

![ConfigBanner](https://strassburger.org/img/lifestealz/banner_config.png)

Here is an example of the configuration file:
<details>
<summary>Click me!</summary>

```yml
#     _      _  __        _____ _             _   ______
#    | |    (_)/ _|      / ____| |           | | |___  /
#    | |     _| |_ ___  | (___ | |_ ___  __ _| |    / /
#    | |    | |  _/ _ \  \___ \| __/ _ \/ _` | |   / /
#    | |____| | ||  __/  ____) | ||  __/ (_| | |  / /__
#    |______|_|_| \___| |_____/ \__\___|\__,_|_| /_____|

# !!! COLOR CODES !!!
# This plugin supports old color codes like: &c, &l, &o, etc
# It also supports minimessage, which is a more advanced way to format messages:
# https://docs.advntr.dev/minimessage/format.html
# With these, you can also add HEX colors, gradients, hover and click events, etc

# If set to true, LifeStealZ will check for updates and let you know if there's a newer version
checkForUpdates: true

# Set the language to any code found in the "lang" folder (don't add the .yml extension)
# You can add your own language files. Use https://github.com/KartoffelChipss/LifeStealZ/tree/main/src/main/resources/lang/en-US.yml as a template
# If you want to help translating the plugin, please refer to this article: https://lsz.strassburger.dev/contributing/localization
lang: "en-US"

# A list of worlds, where the plugin should take effect
worlds:
  - "world"
  - "world_nether"
  - "world_the_end"

# The amount of hearts a player has, when joining for the first time
startHearts: 10
# The maximal amount of hearts, a player can have
maxHearts: 20
# The amount of hp a player should have after getting eliminated
respawnHP: 1
# The minimal amount of hearts. If a player gets to this amount of hearts, they will be eliminated.
# PLEASE ONLY CHANGE IF YOU KNOW WHAT YOU ARE DOING!
minHearts: 0
# This option will enforce the heart limit on admin commands like /lifestealz hearts <add, set> <player> <amount>
enforceMaxHeartsOnAdminCommands: false

# If hearts should be dropped instead of directly added to the killer
dropHearts: false
# If a heart should be dropped, when the killer already has the max amount of hearts
dropHeartsIfMax: true
# If a player should lose a heart, when dying to hostile mobs or falldamage, lava, etc
looseHeartsToNature: false
# If a player should lose a heart, when being killed by another player
looseHeartsToPlayer: true
# Whether it should be announced, when a player got eliminated (has no more hearts)
announceElimination: true

# Allows players to withdraw a heart, even if they only have one left
allowDyingFromWithdraw: true
# If the totem effect should be played, when you use a heart
playTotemEffect: true
# The time you have to wait, before you can use another heart in Milliseconds
heartCooldown: 0
# How many times a player can be revived. Set to -1 to make it infinite
maxRevives: -1

# If the use of totems of undying should be prevented
preventTotems: true
# If crystalpvp should be disabled
preventCrystalPVP: true

# Only disable this option if you want to add custom commands on elimination and don't want the player to get banned
disablePlayerBanOnElimination: false
# If the killer should gain a heart on elimination
heartRewardOnElimination: true

# Execute custom commands on events:
# You can use &player& to insert the player name
# For example: tempban &player& banreason 1d
eliminationCommands:
# - "say &player& got eliminated"
# - "niceCommandtwo"

heartuseCommands:
# - "say &player& used a heart item"

reviveuseCommands:
# - "say &player& revived &target&"

heartGainCooldown:
  # A cooldown for how often people can gain a heart.
  enabled: false
  # How long the cooldown should be in Milliseconds
  cooldown: 120000
  # Drops the heart on the ground if a player kills someone, while still on cooldown
  dropOnCooldown: true
  # Prevents picking up hearts from the groun while on cooldown
  preventPickup: true

antiAlt:
  # If the anti alt system should be enabled
  enabled: true
  # If possible alt kill attempts should be logged
  logAttempt: true
  # If possible alt kill attempts should be prevented
  preventKill: false
  # If a message should be sent to the player, when an alt kill attempt is detected
  sendMessage: false
  # Add custom comamnds, to be executed when a possible alt kill attempt is detected
  # You can use &player& to insert the player name (commands are executed for both players)
  commands:
  # - "say Please don't kill alts"
  # - "ban &player& 1h"

storage:
  # The type of storage to use. You have the following options:
  # "SQLite", "MySQL"
  type: "SQLite"

  # This section is only relevant if you use a MySQL database
  host: "localhost"
  port: 3306
  database: "lifestealz"
  username: "root"
  password: "password"

# Here you can modify everything about the custom items
items:
  # DONT DELETE THE defaultheart ITEM!!!
  defaultheart:
    name: "&cHeart"
    lore:
      - "&7Rightclick to use"
    #     - "This would be a second line"
    #     - "And this possibly a third line"
    material: "NETHER_STAR"
    enchanted: false
    customModelData: 100
    # Custom item type for the item ("heart" or "revive")
    customItemType: "heart"
    # When customItemType is "heart", this value is used to determine how many hearts the item gives
    customHeartValue: 1
    # true if this item should be craftable
    craftable: true
    recipe:
      # Every item represents one slot in the crafting table
      # The first item in a row is the left most item in the crafting table
      # If you want a slot to be blank, use 'AIR' or 'empty'
      # If you want to use other custom item (like hearts) use the custom item name (e.g. "defaultheart")
      rowOne:
        - "GOLD_BLOCK"
        - "GOLD_BLOCK"
        - "GOLD_BLOCK"
      rowTwo:
        - "OBSIDIAN"
        - "NETHER_STAR"
        - "OBSIDIAN"
      rowThree:
        - "DIAMOND_BLOCK"
        - "DIAMOND_BLOCK"
        - "DIAMOND_BLOCK"
    sound:
      enabled: true
      sound: ENTITY_PLAYER_LEVELUP # Find all sounds here: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Sound.html
      volume: 1.0
      pitch: 1.0

  revive:
    name: "&dRevive Crystal"
    lore:
      - "&7Rightclick to use"
    material: "AMETHYST_SHARD"
    enchanted: true
    customModelData: 101
    customItemType: "revive"
    customHeartValue: 0
    craftable: true
    recipe:
      rowOne:
        - "AMETHYST_SHARD"
        - "NETHERITE_BLOCK"
        - "AMETHYST_SHARD"
      rowTwo:
        - "OBSIDIAN"
        - "BEACON"
        - "OBSIDIAN"
      rowThree:
        - "AMETHYST_SHARD"
        - "NETHERITE_BLOCK"
        - "AMETHYST_SHARD"
    sound:
      enabled: false
      sound: ENTITY_PLAYER_LEVELUP
      volume: 1.0
      pitch: 1.0

  # You can add as many custom items as you want
```
</details>

If you want a slot in the crafting recipe to be blank, replace the block name with `AIR`.

### WorldGuard Flags

To set a custom worldguard flag, you have to use `/rg flags` and scroll to the last page.

There you can set the following flags:
- **heartloss** - Allow heart loss in this region

<bR>

---

![PlaceholderBanner](https://strassburger.org/img/lifestealz/banner_placeholder.png)

If you are using [Placeholderapi](https://www.spigotmc.org/resources/placeholderapi.6245/) on your server, you can use the following placeholders:

- **%lifestealz_hearts%** - The amount of hearts a user has
- **%lifestealz_maxhearts%** - The maximum amount of hearts a user can have
- **%lifestealz_health%** - The current health, that the player has (half hearts rounded up)
- **%lifestealz_revived%** - The amount of times a player has been revived
- **%lifestealz_craftedhearts%** - The amount of times a player has crafted a heart
- **%lifestealz_craftedrevives%** - The amount of times a player has crafted a revive crystal

<br>

---

![PlaceholderBanner](https://strassburger.org/img/lifestealz/banner_support.png)

If you need help with the setup of the plugin, or found a bug, you can join my discord [here](https://discord.com/invite/Cc76tYwXvy).

[![discord-plural](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/social/discord-plural_vector.svg)](https://strassburger.org/discord)

[Spigot Page](https://www.spigotmc.org/resources/lifestealz.111469/)

---

[![Usage](https://bstats.org/signatures/bukkit/LifeStealZ.svg)](https://bstats.org/plugin/bukkit/LifeStealZ/18735)
