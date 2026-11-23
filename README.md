# Primal Chaos – FusionShop Config (ARK: Survival Ascended)

A ready-to-use shop for the **Primal Chaos** mod on **ARK: Survival Ascended**, made for the **FusionShop** server plugin (AsaApi).

The shop adds **22 categories** and **837 shop entries** (over 1,000 buyable items) covering the mod's progression:
consumables, resources, summon items, structures, tools, armor, saddles, eggs, **every Primal Chaos dino** and **tamed bosses**.

> 🇫🇷 Version française disponible : `config_primalChaos_FR.json` (voir la section [En français](#en-français) plus bas).

---

## Files

| File | Language |
|---|---|
| `config_primalChaos_EN.json` | English |
| `config_primalChaos_FR.json` | French |

Both files contain the same entries, prices and blueprints. Only the display text (category names, descriptions) differs.
Use **one** of them, not both: they use the same packet names.

## Requirements

- ARK: Survival Ascended dedicated server with the **Primal Chaos** mod installed
- **AsaApi** with the **FusionShop** plugin (written for FusionShop **v1.21**)

## Installation

The files only contain the shop part of a FusionShop config: `ShopCategories` and `ShopPackets`.
They do **not** contain the `Mysql`, `General`, `Messages`, `DiscordLog` or `GroupPrivileges` sections, so they can't be loaded on their own.

1. Back up your FusionShop `config.json`.
2. Open the Primal Chaos file in your language.
3. Copy every object from its `ShopCategories` list and **append** them to the `ShopCategories` list of your `config.json`.
4. Do the same for `ShopPackets`.
5. Check that the result is valid JSON (for example with [jsonlint.com](https://jsonlint.com)), then reload the plugin or restart the server.

All categories use `"IncludeGroups": ["Default"]`. Change this if your permission groups use a different name.

Packet names start with `PC_` and category names start with `PC `, so they won't collide with your existing entries.
They are also easy to find and remove if you want to uninstall the shop.

## What's included

| Category | Entries | Price range (points) |
|---|---:|---:|
| PC Blood/Narcotics | 17 | 40 – 3,000 |
| PC Fruits/Seeds | 6 | 300 – 400 |
| PC Unfertilized Eggs | 12 | 60 – 1,500 |
| PC Kibbles | 12 | 100 – 6,000 |
| PC Potions/Paste/Misc | 13 | 50 – 10,000 |
| PC Resources | 18 | 50 – 3,000 |
| PC Summon Items | 16 | 2,500 – 20,000 |
| PC Structures | 5 | 100 – 5,000 |
| PC Tools/Weapons/Ammo | 11 | 50 – 800 |
| PC Armor | 16 | 50 – 36,000 |
| PC Fertilized Eggs | 6 | 150 – 2,600 |
| PC Saddles Toxic/Beta | 78 | 150 – 220 |
| PC Saddles Alpha | 78 | 300 – 450 |
| PC Saddles Elemental/Shadow/Fairy | 43 | 600 – 1,500 |
| PC Saddles Mythic/Fabled/Legendary | 38 | 1,800 – 2,700 |
| PC Saddles Endgame | 48 | 4,000 – 25,000 |
| PC Dinos Toxic/Beta | 95 | 500 – 3,500 |
| PC Dinos Alpha | 94 | 1,000 – 5,250 |
| PC Dinos Elemental | 86 | 2,000 – 7,000 |
| PC Dinos Shadow/Fairy/Mythic/Fabled/Legendary | 68 | 3,500 – 8,750 |
| PC Dinos Angelic/Demonic/Spirit/Chaos | 49 | 8,000 – 20,000 |
| PC Tamed Bosses | 28 | 15,000 – 30,000 |

Some entries let the player pick a variant: fertilized eggs, armor pieces, tools, tranq ammo, Origin and Nightmare tokens/summons.

## Pricing

Prices were balanced for a server where players earn **15 points every 15 minutes** (60 points per hour of play).
They follow the mod's tier ladder: the harder an item is to get through normal play, the more it costs.

```
Toxic / Beta → Alpha → Electric / Hydro / Volcanic → Shadow / Fairy
→ Mythic / Fabled / Legendary → Angelic / Demonic → Origin → Spirit / Chaos → Nightmare / Death Knight
```

- **Dinos** are priced by tier and by species size (a Toxic Rex costs more than a Toxic Dodo). All dinos spawn at **level 224** with a random gender.
- No regular dino costs more than **20,000** points; tamed bosses go up to **30,000**.
- **Equipment** (tools, armor, saddles) comes with a **random quality** that improves with the tier, using FusionShop's `"min;max"` syntax.

If your server gives more or fewer points, scale the `Price` values to match.

## Command-based entries

Some blueprint paths in the Primal Chaos mod don't load in FusionShop (the mod moved files between versions).
These **76 entries** use admin commands instead, which find the item or dino by class name:

- Items: `cheat gfi <ClassName> <amount> <quality> 0`
- Dinos and bosses: `cheat GMSummon "<ClassName>" 224`

They run with `"AsAdmin": true`. They don't show an item icon in the shop, and command-spawned dinos may have a different gender than the blueprint-based ones.

Affected entries include the Beta (water), Electric, Mythic, Legendary and Demonic dinos, the tamed Elemental Guardians and Death Knight, Nightmare, Guardian, Chaos titan and Death Knight summons, Toxic Cloth armor, some hides, and some eggs.

## Not included

- **Omega** dinos and items: removed from the mod.
- **Demonic Rocket Launcher**, its rockets, Electronics/Polymer Demonic: deprecated.
- **Hydro Dodo Rex**, **Demonic Thorny**, **Angelic BOSS soul**: broken in the mod's spawn-code list.
- **Tameable Death Knight summon** and **Chaos Bed**: don't work in-game.

## Known limits

- Tested on one server only. If FusionShop logs `Failed to load class ...` for an entry after a mod update, that entry's blueprint path has changed.
- These four dinos don't spawn naturally in the wild and may have unusual stats: Shadow Diplo, Fabled Mantis, Mythic Owl, Spirit Quetz.

Found a broken entry or a wrong path? Please [open an issue](../../issues).

## Credits

- **Primal Chaos** mod by its authors.
- Tier and progression info from the Primal Chaos guide by Rokitur.
- Item and dino codes from the Primal Chaos engram and spawn-code sheets.

This config is a community resource and is not affiliated with the Primal Chaos authors or with Studio Wildcard.

---

## En français

Configuration de boutique **FusionShop** pour le mod **Primal Chaos** sur **ARK: Survival Ascended** : 22 catégories et 837 articles (consommables, ressources, invocations, structures, outils, armures, selles, œufs, tous les dinos Primal Chaos et des boss apprivoisés).

**Installation :** sauvegardez votre `config.json`, puis ajoutez le contenu des listes `ShopCategories` et `ShopPackets` de `config_primalChaos_FR.json` à la fin des listes du même nom dans votre `config.json`. Vérifiez que le JSON est valide et rechargez le plugin. N'utilisez qu'une seule langue (FR ou EN), pas les deux.

**Prix :** pensés pour un gain de **15 points toutes les 15 minutes**. Les dinos sont au niveau 224, avec un maximum de 20 000 points ; les boss apprivoisés vont jusqu'à 30 000 points. Ajustez les champs `Price` si votre serveur donne plus ou moins de points.

Un article ne fonctionne pas ? [Ouvrez une issue](../../issues).
