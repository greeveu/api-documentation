# Api Documentation - DEPRICATED
## This API is now Depricated. Use https://api.greev.eu/v2/swagger-ui/index.html instead and https://api.greev.eu/v2/api-docs to get the OpenAPI JSON.

This is the documentation for the public greev.eu API, for now this will be a rather basic documentation and we will update it when needed.




##### API Base URL

The base URL for the current api is: `https://api.greev.eu/v2` from now on all calls will omit the base part.




#### General Infos

We will define placeholders with the following formatting: `{PLACEHOLDER}`

All UUID __have to be__ the long variant with dashes.




### Player Stats

In order to get the Player specific stats you can call the following endpoint: `/player/stats/{UUID}` eg.: `/player/stats/01cba8c4-ef9d-4ff9-aee3-5ba4bb38c3c8`

Games for which a player doesn't have stats for will not appear in response.




### Top Lists for Games

To get the TOP X Users for a gamemode you can call the `/stats/{game}/top?count={count}&offset={offset}`



The game placeholder can be any of those games: 

```
bedwars
skywars
knockpvp
knockffa
rush
oneline
quake
1vs1
mlgrush
qsg
mlgrush
uhc
sumo
cores
spleef
bowspleef
fastbridge
fastbridge_inclined
fastbridge_short
fastbridge_inclined_short
fastbridge_staircase
tntrun
jumpleague
tokens
loginstreak
performance
```

The `count` and `offset` have to be any number. 
`Count` can be at max 50 and must be at least 1.
`Offset` can be any number above or 0.




### Player stats for a specific Gamemode

In order to get the gamemode stats for a specific player you can use the following url: `/stats/{game}/player/{uuid}`

The `game` placeholder has the one of the valid gamemodes from the list above.

The `uuid` again has the be a user uuid with dashes.


### Player stats for the Adventcalender

To get the times, fails, checkpoints etc stats for the advent calender you can use the following url: `/stats/advent/top/{year}/{id}?count={count}&offset={offset}`


`year` has to be a year in which the event was hosted, like 2019 or 2020.  

`id` is the jumpandrun id / day. It has to be between 1 and 24.

`Count` can be at max 50 and must be at least 1.  

`Offset` can be any number above or 0.  


### Player Name, UUID and Name History

__This endpoint will cache the results and have no SLO.__

To get the UUID of a player you can use `/player/uuid/{name}`

To get the Name of a player you can use `/player/name/{uuid}`  

And to get the Name History of a player you can use `/player/namehistory/{uuid}`

Where the `name` has to be a valid Minecraft name and the `uuid` has to be a valid Minecraft uuid with dashes.
