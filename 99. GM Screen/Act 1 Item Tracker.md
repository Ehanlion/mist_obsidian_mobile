_ _ _ _
#### Item Tracker Guide
This tracker is used to list when magic items are gained or lost by the party as a historical tracker for me. 

**Format**
`Date, item, rarity, attunement, 10-word-description`
_ _ _ _

Unicorn Greatsword

Ring of Spellcasting
Terracotta Amulet
Raven statue
Wand of Wonder
Eldritch Rod
Stone of Goodluck
Pipe of Smoke Display
Disguise Self Tattoo
Manta Ray Cloak
Home Gambling Solution
Elven Chain

GBT's Guide to Fighting
Bloodspear
+1 Trident
+1 Greatsword
+2 Maul
Terracotta Shield
Don't Rattle My Bones
Mace of Disruption
Dragontooth Dagger
Breastplate (water) ?
Cap (water) ? -> cap of water breathing
Bottomless Tankard of Beer
Green Order COmpass
Armor of Fungal Spores

+1 Focus
Tent of Many Things
Clockwork Amulet
Clock of the Savant
Ashen Treaders
Wand of Aquafire
Propellor Helm
Wand of Magic Missile

Ring of Puzzler's Wite
Bell Branch
Propellor Helm

Invisible Lantern Thing
Bernhard's Wedding Rings

```
common = 1
uncommon = 2
rare = 3
very rare = 4
legendary = 5
mythic = 6
```

| Date       | Item               | Rarity | Count |
| ---------- | ------------------ | ------ | ----- |
| 2025-04-05 | Propeller Cap      | 1      | 1     |
| 2025-04-05 | Pike of Subduction | 3      | 1     |
| 2025-04-12 | Bernhard's Rings   | 5      | 1     |
| 2025-04-12 | Symbiotic Armor    | 4      | 1     |
| 2025-04-19 | Item 1             | 2      | 1     |
| 2025-04-19 | Item 2             | 3      | 1     |
| 2025-04-26 | Item 3             | 1      | 1     |
^TestTable

**Testing charts**
Trying to plot on `xAxis` the date, and on `yAxis` to plot `Rarity and Counts` of all items given on that day. 
```chart
type: bar
id: TestTable
labels: []
select: [Rarity, Count]
series:
  - title:
    data: []
width: 100%
beginAtZero: true
xTitle: Date of Items
stacked: false
```


| Sessions   | Common | Uncommon | Rare | Very Rare | Legendary | Potions |
| ---------- | ------ | -------- | ---- | --------- | --------- | ------- |
| 2025-04-12 | 0      | 0        | 1    | 1         | 0         | 0       |
| 2025-04-19 | 0      | 0        | 0    | 1         | 1         | 3       |
^TestTable3

```chart
type: bar
id: TestTable3
labels: []
select: [Common, Uncommon, Rare, Very Rare, Legendary, Potions]
series:
  - title:
    data: []
width: 100%
beginAtZero: true
indexAxis: x
stacked: false
```