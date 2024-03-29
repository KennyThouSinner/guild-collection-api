Guilds-Collection-API

An API to make your life simpler with getting guilds and their props.

How our API works:

Gets the guild by the provided ID -> Returns the guild ID and the whole guild Object depending on the function you used

Gets guild owner by the provided ID -> Returns the owner's ID and the whole owner's user object

Gets the guild by the provided ID -> Returns a collection depending on the function you used



Functions you can use with our API:

```js
/**
*~ getGuild (by the provided guild ID)
*~ getOwner (by the provided guild ID)
*~ getGuildInfo (by the provided guild ID, returns the full guild Object) [REPLACED]
*~ getOwnerInfo (by the provided guild ID, returns the full owner user Object) [REPLACED]
*~ getChannelsByType (by the provided guild ID and provided channel type) -- [E.g. -> "text"]
*~ getAllChannelsByObject (by the provided guild ID, returns every channel by their object)
*~ getAllChannelsByName (by the provided guild ID, returns every channel by it's name)
*~ getAllChannelsByID (by the provided guild ID, returns every channel by it's id)
*~ getAllChannelsWithTimeout (by the provided guild ID, returns every channel that has a timeout)
*~ getAllNSFWChannels (by the provided guild ID, returns every channel that's flagged as NSFW)
*/
```
Examples and how to use:


~ getGuild:

```js
const Discord = require("discord.js")
const client = new Discord.Client();
const { Info } = require("guild-collections-api");

console.log(new Info(client).getGuild("603009265346805760")) 

/*
*'603009265346805760' is the guild ID, you can only input guild IDs. 
*Be careful when doing 'new Info()', in the '()' you're suppose to input whatever you declared Discord.Client as
*/
```

~ getGuild (extended):

```js
const Discord = require("discord.js");
const client = new Discord.Client();
const { Info } = require("guild-collections-api");

console.log(new Info(client).getGuild("603009265346805760", true)) 
//Passing a boolean maps it by name + member count, if it's true, it'll return with the name, if it's false or not included, it'll return the object

//Warning: BOOLEANS CAN NOT BE USED IN FUNCTIONS THAT RETURN OBJECTS ONLY
```


~ getChannelsByType

```js
const Discord = require("discord.js")
const bot = new Discord.Client();
const { Info } = require("guild-collections-api");

console.log(new Info(bot).getChannelsByType("603009265346805760", "text"))

/*
* In the 'getChannelsByType' function you have to provide 2 paramaters, the guild ID and the channel type.
* Otherwise it won't work and will throw an error.
* Side note: Passing a boolean after 'type' will result in it mapping the channels by name
*/
```


You can find our extended documentation in our ~~[github repo](https://github.com/KennySinners/guild-collection-api/blob/master/Documentation.md)~~

Working link:

https://github.com/KennySinners/guild-collection-api/blob/master/Documentation.md
