---
layout: post
draft: false
path: "/posts/riot-games-api/"
tags: 
  - Default
description: "League of Legends (abbreviatedLoL) is amultiplayer online battle arena
[https://en.wikipedia.org/wiki/Multiplayer_online_battle_arena] video game
developed and published byRiot Games [https://en.wikipedia.org/wiki/Riot_Games]
 forMicrosoft Windows [h..."
title: "Riot Games Api"
date: "2018-01-25T00:26:57.000Z"
slug: "/riot-games-api/"
feature_image: null
author: "Nir Adler"
---

> _**League of Legends**_ (abbreviated _**LoL**_) is a [multiplayer online battle arena](https://en.wikipedia.org/wiki/Multiplayer_online_battle_arena "Multiplayer online battle arena") video game developed and published by [Riot Games](https://en.wikipedia.org/wiki/Riot_Games "Riot Games") for [Microsoft Windows](https://en.wikipedia.org/wiki/Microsoft_Windows "Microsoft Windows") and [macOS](https://en.wikipedia.org/wiki/MacOS "MacOS"). The game follows a [freemium](https://en.wikipedia.org/wiki/Freemium "Freemium") model and is supported by [microtransactions](https://en.wikipedia.org/wiki/Microtransaction "Microtransaction"), and was inspired by the _[Warcraft III: The Frozen Throne](https://en.wikipedia.org/wiki/Warcraft_III:_The_Frozen_Throne "Warcraft III: The Frozen Throne")_ [mod](https://en.wikipedia.org/wiki/Mod_(video_gaming) "Mod (video gaming)"), _[Defense of the Ancients](https://en.wikipedia.org/wiki/Defense_of_the_Ancients "Defense of the Ancients")_.[\[1\]](https://en.wikipedia.org/wiki/League_of_Legends#cite_note-1up-dotagenre-1)

League of legends or lol is a popular game with an [active api](https://developer.riotgames.com) with the following highlights:

Dynamic API:![](https://blog.prototypesart.net/wp/wp-content/uploads/2018/01/api-136x300.png)

*   get champions data - [https://eun1.api.riotgames.com/lol/platform/v3/champions?freeToPlay=false&api\_key=](https://eun1.api.riotgames.com/lol/platform/v3/champions?freeToPlay=false&api_key=) (my usage of the api to [get champions that are free to play to my free to play widget](https://github.com/niradler/lol-freeToPlay-client))
*   [https://eun1.api.riotgames.com/lol/static-data/v3/champions?locale=en\_US&tags=all&dataById=true&api\_key=](https://eun1.api.riotgames.com/lol/static-data/v3/champions?locale=en_US&tags=all&dataById=true&api_key=) (get all chmapions with details: abilities, skins etc.)
*   get summoner data
*   create tournament
*   game statistic
*   game status

Static Data:

*   usage: - Profile Icons:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/profileicon/588.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/profileicon/588.png)
*   Champions:  
    [http://ddragon.leagueoflegends.com/cdn/img/champion/loading/Aatrox\_0.jpg](http://ddragon.leagueoflegends.com/cdn/img/champion/loading/Aatrox_0.jpg) (replace 0 with +1 to change skins)
*   Items:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/item/1001.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/item/1001.png)
*   Masteries:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/mastery/6111.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/mastery/6111.png)
*   Runes:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/rune/8001.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/rune/8001.png)
*   Summoner Spells: - [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/passive/Cryophoenix\_Rebirth.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/passive/Cryophoenix_Rebirth.png)
*   [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/spell/FlashFrost.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/spell/FlashFrost.png)
*   [http://ddragon.leagueoflegends.com/cdn/6.24.1/img/spell/SummonerFlash.png](http://ddragon.leagueoflegends.com/cdn/6.24.1/img/spell/SummonerFlash.png)
*   info: - Profile Icons:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/profileicon.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/profileicon.json)
*   Champions:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/champion.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/champion.json)
*   Individual Champions:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/champion/Aatrox.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/champion/Aatrox.json)
*   Items:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/item.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/item.json)
*   Masteries:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/mastery.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/mastery.json)
*   Runes:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/rune.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/rune.json)
*   Summoner Spells:  
    [http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en\_US/summoner.json](http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/summoner.json)

**Notes**

> after the last time i played with the api and it was very long to get application approve back then, and the riot api limit is a nightmare for developer, this time it was
> 
> much faster and the response was positive!:)
> 
> what make the development a bit easier although i will recommend using some sort of caching mechanism, to avoid riot limit on a certain api.
> 
> [https://github.com/niradler/lol-freeToPlay](https://github.com/niradler/lol-freeToPlay) in my server i will query the api once in an hour, and then response from local data.
> 
> my free to play widget [GitHub](https://github.com/niradler/lol-freeToPlay-client)

Your browser does not support iframes.
    