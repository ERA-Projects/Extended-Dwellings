The mod allows you to configure up to 4 slots for each city dwelling.
Each slot can be either an alternative creature or an additional one.

The alternate creature uses the same population counter as the native creature. However, an arbitrary ratio between the original number of creatures and the alternative can be specified.
For example, 1 golem can be purchased to replace a population of 12 gremlins. Such slots are called alternative, since it is impossible to buy the maximum of creatures from all alternative slots. Purchasing creatures in one of the slots proportionally reduces the number of creatures in the others.

Additional slots are not associated with the main population of dwellings. Their population can be set manually via EPM
or it can grow automatically weekly, as happens with native inhabitants of homes.

Use the following documented EPM functions:
"dex_DwellingPopulation" to set/change the population in the additional slot.
"dex_SetDwellingSlotByTownType" to configure a slot for all cities of a certain type.
"dex_GetDwellingSlotByTownType" to get the slot settings for all cities of a certain type.
"dex_SetDwellingSlotByTownId" to configure a slot in a specific city (takes precedence over dex_SetDwellingSlotByTownType).
"dex_GetDwellingSlotByTownId" to get the slot setting in a specific city (takes precedence over dex_GetDwellingSlotByTownType).

For older mods that depend on the battery.dll plugin, there is a function "dex_CA_D" with almost identical CA:D syntax.
It is recommended, if possible, to still use the new API for more accurate and simplified slot configuration, including alternatives and
auto-growing population.

Example:
!?FU(OnAfterErmInstructions);
!!re i/0/8:;
 !!FU(dex_SetDwellingSlotByTownType):Pi/0/0/2/120/-1007;
!!en:;
For each type of city, assigns an additional slot to an unimproved dwelling of the 1st level with an auto-growing population of 7 psych. elementals per week (14 with castle, 21 with Grail).
!?FU(OnAfterErmInstructions);
!!re i/0/8:;
 !!FU(dex_SetDwellingSlotByTownType):Pi/0/0/2/120/5;
!!en:;
Same thing, but elementals are ALTERNATIVES to siblings and can be recruited at a rate of 1 elemental instead of 20 siblings (5% = 1/20).