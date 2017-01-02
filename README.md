# DiamondGuarantee

I created this Minecraft server plugin using the Bukkit API to fix starvation issues with rare resources like diamonds, glowstone, nether wart, and elytras.  In Vanilla multiplayer, all of these quickly disappear from areas of the world, making it difficult for players who come later to gather those resources.  DiamondGuarantee ensures that players who are making a real effort (as opposed to trying to farm or cheat) will find those resources.  For example, it will add new diamond ores for players who are mining to find, and adds glowstone dust / nether wart drops to some nether monsters (with some anti-farming logic as well), and guarantees the ender dragon will drop an elytra on death.

I stopped working on this project after Minecraft 1.10.  Anyone may use my source code to continue the project, but see the LICENSE file for restrictions.



Guarantee players who put in the work will find diamonds!
Even when faced with hoarders, cheaters, and just plain bad luck.

![diamondguarantee_ad](https://s30.postimg.org/krwi2wwr5/diamondguarantee_ad.png)

This plugin works very well for Minecraft 1.10, and some earlier versions are available for older versions of Minecraft. However, it will not be updated for future Minecraft versions because I've finally retired from Minecraft development (5 years of plugins!), and I'm moving on to develop indie games. :) You can follow me in my adventures here: 

facebook.com/BigScaryGames

Despite the mining limiters and anti-x-ray solutions you've probably added to your server, areas can still run low on diamond ore and other desirable rares due to many factors - hoarding, greed, overpopulation, cheating, and randomness in Vanilla world gen. This problem is worst when new players get frustrated and quit your server before they've given it a fair assessment.

DiamondGuarantee solves the diamond starvation problem by detecting when a miner is having a streak of bad luck, then cleverly injecting diamond ores just out of sight where he's sure to discover them! It also ensures players can get glowstone and nether wart, and have an opportunity to battle the Ender Dragon (all configurable, and disable-able).

**Features**

All features can be tweaked or even entirely disabled on a per-world basis.

Sad Player Detection - Monitors a player's ratio of stone blocks to diamond ore broken to determine when a player is having unreasonably poor luck discovering diamonds. Under the default configuration, players will find diamonds at the same rate they would in a brand new Vanilla world, even in areas which have been explored previously.

Discreet Happiness Injection - Players won't notice the plugin adding diamond ores, because ores will only ever be inserted when they're entirely surrounded by stone. X-rayers could theoretically see it in action, but their efficiency at finding ores will prevent them from ever generating an ore via this plugin.

Bad Guy Rejection - Technical details prevent clever players from gaming the system, for example by using pistons to push diamond ore out of the diamond zone for free breaks, using TNT to anonymously collect diamonds from the world, or manufacturing a favorable diamond/stone ratio by placing stone blocks just to break them again.

Advanced-Player Protection - Some players like to use silk touch to break an ore, then store it for breaking with a different (fortune?) tool later. They won't be penalized for either.

Renewable Glowstone - Ghasts will drop 20 glowstone dust (configurable) when slain. This renewable source of glowstone guarantees players who make the effort and spend time in The Nether can get their hands on glowstone, even when many other players have previously explored the same area. As a bonus, this gives players a reason to risk approaching ghasts and waiting until they're over solid ground before killing them, which makes for a more exciting encounter (which is otherwise disappointingly rare in The Nether!).

Renewable Nether Wart - In Nether Fortresses, pig zombies now have a 20% (configurable) chance to drop a single nether stalk. Now players can always find nether wart, even in areas previously explored by others. This solution carries a bonus - it gives players reason to pick a fight with pig zombies, which can quickly turn The Nether into a very dangerous place!

Renewable Dragon Rewards - When the Ender Dragon dies, he'll always drop a dragon egg trophy as an item.

Renewable Elytras - When the Ender Dragon dies, he'll always drop an elytra, so all players can earn one.

**Installation**

Download DiamondGuarantee.jar into your server's plugins folder, then /reload or reboot your server.

How Diamond-Related Settings Work

The default configuration guarantees diamonds at the Vanilla rate - assuming efficient mining strategies like branch mining - without changing gameplay. You can tweak the settings to make diamonds more plentiful, or to require worse bad luck before the plugin will inject ore.

The concept is simple - players get invisible points for breaking stone (value depends on Y level where the block is broken), and lose points for breaking diamond ore. If a player's score reaches a level you specify, the plugin will generate an ore for the player to find (which, due to its placement, will be very difficult to miss). Blocks placed by players don't grant or subtract points when they're broken.

Diamonds will only ever be generated in the "diamond zone" in "normal" worlds. If your worlds aren't generated using the default world generator with default settings, then you should check and possibly adjust the diamond zone settings in the config file.

All config settings are per-world, so you can tweak settings for specific worlds.

How to Test Your Settings
Climb down to the diamond zone you've set in your config file.
Find a natural stone block where you can't see the block behind it (don't place blocks for testing - blocks placed by players will be ignored by the plugin).
Execute /SetDiamondScore <your name> <your diamond value setting>.
Break the block.
Assuming the hidden block behind your stone block was also stone, you'll find a diamond. If you check your /DiamondScore <your name>, then you'll see your score has been reduced due to a diamond being generated for you. Breaking further stone blocks won't generate more diamonds until you've reached the diamond value again.

**Commands**

Use /DGReload to reload settings from the config file.

Use /DiamondScore to check a player's current score.

Use /SetDiamondScore to change a player's current score.


**Permissions**

All your players will benefit from the plugin. These permission nodes control who has access to administrative features.

diamondguarantee.admin.* will conveniently grant all of the following permissions:

diamondguarantee.reload

diamondguarantee.getscore

diamondguarantee.setscore
