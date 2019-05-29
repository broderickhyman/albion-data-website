---
layout: default
---
**!! THIS PROJECT IS STILL IN BETA !!**

Welcome to the Albion Data Project!

The goal of this project is to collect and distribute realtime information for Albion Online. This is achieved with a downloadable client that monitors network traffic specifically for Albion Online, identifies the relevant information, and then ships it off to a central server which distributes the information to anyone who wants it.

[Click here to download the client.](https://github.com/BroderickHyman/albiondata-client/releases)

This process is run on a [DigitalOcean Droplet](https://www.digitalocean.com) in order to ensure almost perfect uptime and high performance for the users. If you find this project beneficial to you then please consider a donation, thanks!!

[![ko-fi](https://www.ko-fi.com/img/donate_sm.png)](https://ko-fi.com/E1E5K69V)

### Player Information
If you would like to help the Albion Data Project, and all the web sites and applications that use the data provided by it, then the best thing you can do is download our client and run it whenever you're playing Albion Online.

The most recent releases can be found here: [https://github.com/BroderickHyman/albiondata-client/releases](https://github.com/BroderickHyman/albiondata-client/releases)

### Where Can I View The Data I Upload?
> Note that the client can only upload the market orders that you load in game, so be sure to browse the market for the prices that you need. When a price is uploaded, it is visible in the data immediately.

The best way to make use of the data is by using the tools that are built on it:

- [AlbionOnline2d](https://www.albiononline2d.com/en/market) pulls the latest information from the database and shows different selling metrics for the Auction Houses.
- [AlbionAssistant](http://albionassistant.com/) utilizes the data to calculate crafting recipe costs and profits.
- More tools are actively being developed. If you want your project listed here, contact us using the info below.

Market data can be also be obtained through the API, which has [Swagger documentation available here](https://www.albion-online-data.com/api/swagger). (Item IDs can be found in the [formatted metadata](https://github.com/broderickhyman/ao-bin-dumps/tree/master/formatted), for use in the API.)

- Current Prices (Table View): [`https://www.albion-online-data.com/api/v2/stats/view/T3_FURNITUREITEM_TROPHY_GENERAL?locations=Caerleon,Bridgewatch`](https://www.albion-online-data.com/api/v2/stats/view/T3_FURNITUREITEM_TROPHY_GENERAL?locations=Caerleon,Bridgewatch)
- Current Prices (JSON): [`https://www.albion-online-data.com/api/v2/stats/prices/T3_FURNITUREITEM_TROPHY_GENERAL?locations=Caerleon,Bridgewatch`](https://www.albion-online-data.com/api/v2/stats/prices/T3_FURNITUREITEM_TROPHY_GENERAL?locations=Caerleon,Bridgewatch)
- Historical Prices (sell orders only): [`https://www.albion-online-data.com/api/v1/stats/charts/T3_FURNITUREITEM_TROPHY_GENERAL?date=4-30-2019&locations=Thetford`](https://www.albion-online-data.com/api/v1/stats/charts/T3_FURNITUREITEM_TROPHY_GENERAL?date=4-30-2019&locations=Thetford)

### Developer Information
If you're building something to consume the data published by the
Albion Data Project here are some things you will need to know:
- NATS Connection String: nats://public:thenewalbiondata@www.albion-online-data.com:4222
- NATS Topics:
  - `goldprices.deduped`
  - `marketorders.deduped`
  - `mapdata.deduped`
- Structure of data messages: [albiondata-client/lib](https://github.com/BroderickHyman/albiondata-client/tree/master/lib)

A note on duplicate messages. As information comes into the NATS Server it is looked at and deduplicated over a 5 minute window. As a subscriber the goal is that you should only get the same message once every 5 minutes. This is of course open for change as we go however. The reason we are sending the same message at all is two fold.

New people connecting to the network may have missed previous messages. Along with that however we don’t have a good way of noticing things like market orders completing. To remove market orders from your application the current best idea around is to keep track of the last time an order was seen, and then after not seeing it for X hours remove it as probably having been completed.

### Related Projects
- [albiondata-client](https://github.com/BroderickHyman/albiondata-client)
- [albiondata-deduper-dotNet](https://github.com/BroderickHyman/albiondata-deduper-dotNet)
- [albiondata-sql-dotNet](https://github.com/BroderickHyman/albiondata-sql-dotNet)
- [albiondata-api-dotNet](https://github.com/BroderickHyman/albiondata-api-dotNet)
- [AlbionData.Models](https://github.com/broderickhyman/albiondata-models-dotNet) [![NuGet](https://img.shields.io/nuget/v/AlbionData.Models.svg)](https://www.nuget.org/packages/AlbionData.Models/)
- [albion-data-website](https://github.com/broderickhyman/albion-data-website) (This website)

### Contact Us
The best way to get in touch with us is on the Albion Online Fansites Discord server in either the #proj-albiondata or the #developers channel. A permanent invite link can be found here: [https://discord.gg/TjWdq24](https://discord.gg/TjWdq24)

### Is This Allowed
> Our position is quite simple. As long as you just look and analyze we are ok with it. The moment you modify or manipulate something or somehow interfere with our services we will react (e.g. perma-ban, take legal action, whatever).

~MadDave, Technical Lead at Sandbox Interactive for Albion Online, [source](https://forum.albiononline.com/index.php/Thread/51604-Is-it-allowed-to-scan-your-internet-trafic-and-pick-up-logs/?postID=512670#post512670)
