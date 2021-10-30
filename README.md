## lua-eluna-test
 
Lua script for Azerothcore with ElunaLUA to test hooks.

#### Find me on patreon: https://www.patreon.com/Honeys


## Requirements:
Compile your [Azerothcore](https://github.com/azerothcore/azerothcore-wotlk) with [Eluna Lua](https://www.azerothcore.org/catalogue-details.html?id=131435473).
The ElunaLua module itself usually doesn't require much setup/config. Just specify the subfolder where to put your lua_scripts in its .conf file.

If the directory was not changed in the ElunaLua config, add the .lua script to your `../lua_scripts/` directory as a subfolder of the worldserver.


## Admin Usage:

- Trigger the events listed below.
- Receive a message in the worldserver console whenever a hook fires.

Commands:

- `luatest` to list all events which weren't tested in this session.
- `resetluatest` to start an new session.

![image](https://user-images.githubusercontent.com/71938210/139537206-365dff58-72f4-4a6b-8975-7f02ccf5dbbf.png)
![image](https://user-images.githubusercontent.com/71938210/139540053-27c1a37d-f55b-4a69-bad6-8922b16885b0.png)



## Currently listed events:

- PLAYER_EVENT_ON_CHARACTER_CREATE = 1        --(event, player)
- PLAYER_EVENT_ON_CHARACTER_DELETE = 2        --(event, guid)
- PLAYER_EVENT_ON_LOGIN = 3                   --(event, player)
- PLAYER_EVENT_ON_LOGOUT = 4                  --(event, player)
- PLAYER_EVENT_ON_SPELL_CAST = 5              --(event, player, spell, skipCheck)
- PLAYER_EVENT_ON_KILL_PLAYER = 6             --(event, killer, killed)
- PLAYER_EVENT_ON_KILL_CREATURE = 7           --(event, killer, killed)
- PLAYER_EVENT_ON_KILLED_BY_CREATURE = 8      --(event, killer, killed)
- PLAYER_EVENT_ON_DUEL_REQUEST = 9            --(event, target, challenger)
- PLAYER_EVENT_ON_DUEL_START = 10             --(event, player1, player2)
- PLAYER_EVENT_ON_DUEL_END = 11               --(event, winner, loser, type)
- PLAYER_EVENT_ON_GIVE_XP = 12                --(event, player, amount, victim) - Can return new XP amount
- PLAYER_EVENT_ON_LEVEL_CHANGE = 13           --(event, player, oldLevel)
- PLAYER_EVENT_ON_MONEY_CHANGE = 14           --(event, player, amount) - Can return new money amount
- PLAYER_EVENT_ON_REPUTATION_CHANGE = 15      --(event, player, factionId, standing, incremental) - Can return new standing
- PLAYER_EVENT_ON_TALENTS_CHANGE = 16         --(event, player, points)
- PLAYER_EVENT_ON_TALENTS_RESET = 17          --(event, player, noCost)
- PLAYER_EVENT_ON_CHAT = 18                   --(event, player, msg, Type, lang) - Can return false, newMessage
- PLAYER_EVENT_ON_WHISPER = 19                --(event, player, msg, Type, lang, receiver) - Can return false, newMessage
- PLAYER_EVENT_ON_GROUP_CHAT = 20             --(event, player, msg, Type, lang, group) - Can return false, newMessage
- PLAYER_EVENT_ON_GUILD_CHAT = 21             --(event, player, msg, Type, lang, guild) - Can return false, newMessage
- PLAYER_EVENT_ON_CHANNEL_CHAT = 22           --(event, player, msg, Type, lang, channel) - Can return false, newMessage
- PLAYER_EVENT_ON_EMOTE = 23                  --(event, player, emote) - Not triggered on any known emote
- PLAYER_EVENT_ON_TEXT_EMOTE = 24             --(event, player, textEmote, emoteNum, guid)
- PLAYER_EVENT_ON_SAVE = 25                   --(event, player)
- PLAYER_EVENT_ON_BIND_TO_INSTANCE = 26       --(event, player, difficulty, mapid, permanent)
- PLAYER_EVENT_ON_UPDATE_ZONE = 27            --(event, player, newZone, newArea)
- PLAYER_EVENT_ON_MAP_CHANGE = 28             --(event, player)
- -- Custom
- PLAYER_EVENT_ON_EQUIP = 29                  --(event, player, item, bag, slot)
- PLAYER_EVENT_ON_FIRST_LOGIN = 30            --(event, player)
- PLAYER_EVENT_ON_CAN_USE_ITEM = 31           --(event, player, itemEntry) - Can return InventoryResult enum value
- PLAYER_EVENT_ON_LOOT_ITEM = 32              --(event, player, item, count)
- PLAYER_EVENT_ON_ENTER_COMBAT = 33           --(event, player, enemy)
- PLAYER_EVENT_ON_LEAVE_COMBAT = 34           --(event, player)
- PLAYER_EVENT_ON_REPOP = 35                  --(event, player)
- PLAYER_EVENT_ON_RESURRECT = 36              --(event, player)
- PLAYER_EVENT_ON_LOOT_MONEY = 37             --(event, player, amount)
- PLAYER_EVENT_ON_QUEST_ABANDON = 38          --(event, player, questId)
- PLAYER_EVENT_ON_LEARN_TALENTS = 39          --(event, player, talentId, talentRank, spellid)
- -- UNUSED                     = 40          --(event, player)
- -- UNUSED                     = 41          --(event, player)
- PLAYER_EVENT_ON_COMMAND = 42                --(event, player, command) - player is nil if command used from console. Can return false
- PLAYER_EVENT_ON_PET_SPAWNED = 43            --(event, player, pet)
