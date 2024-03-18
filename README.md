# Fortunate
Fortunate is a data pack that reworks how Fortune works.

Fortune's drop increasing is now built into the ore, and Fortune just increases the chances of getting these extra ores.
Some other minor changes are that Gold now drops 1-3 Raw Gold without the Fortune rolls, and that Emerald ore drops 2-4 ores without Fortune rolls. 

This pack was made to buff ores for players who are not interested in following metas, such as waiting on Fortune III and trying to get it ASAP, or making farms to get their ores.

Happy Spelunking everybody.

## Configuring the Data Pack
This datapack is licensed under the MIT license, which means you're free to modify it provided you don't remove the LICENSE from the root folder.

### Changing the Fortune chances
Fortune chances can be modified by going into `data/fortunate/predicates/fortune_chances.json`, and modifying the values that are present there.
The array starts at level 0 and increases by 1 level for each value.

### Adding Modded Ores
Modded ores are not included by default, however, they are easily includable by doing the following:
```diff
{
    ...
    "type": "minecraft:item",
    "functions": [
-       {
-           "enchantment": "minecraft:fortune",
-           "formula": "minecraft:ore_drops",
-           "function": "minecraft:apply_bonus"
-       },
+       {
+           "function": "minecraft:reference",
+           "name": "fortunate:add_with_fortune"
+       }
        ...
    ],
    "name": "example:my_cool_material"
}
```
If you have a specific case like Redstone, where more than one ore will drop, you can copy `data/fortunate/item_modifiers/add_with_fortune` and replace the `"count"` value with your specified value.