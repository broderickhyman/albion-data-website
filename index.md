---
layout: default
---
**!! THIS PROJECT IS STILL IN BETA !!**

**!! These tools are not affiliated with Albion Online or Sandbox Interactive GmbH !!**

Welcome to the Albion Data Project!

The goal of this project is to collect and distribute realtime information for Albion Online. This is achieved with a downloadable client that monitors network traffic specifically for Albion Online, identifies the relevant information, and then ships it off to a central server which distributes the information to anyone who wants it.

[Click here to download the client.](https://github.com/BroderickHyman/albiondata-client/releases)

[Client download stats](https://www.somsubhra.com/github-release-stats/?username=broderickhyman&repository=albiondata-client)

### Contributing
This process is run on a [DigitalOcean Droplet](https://www.digitalocean.com) in order to ensure almost perfect uptime and high performance for the users. If you find this project beneficial to you then please consider a donation, thanks!!

[Become a Patron!](https://www.patreon.com/bePatron?u=10422119)

[![ko-fi](https://www.ko-fi.com/img/donate_sm.png)](https://ko-fi.com/E1E5K69V)

### Player Information
If you would like to help the Albion Data Project, and all the web sites and applications that use the data provided by it, then the best thing you can do is download our client and run it whenever you're playing Albion Online.

The most recent releases can be found here: [https://github.com/BroderickHyman/albiondata-client/releases](https://github.com/BroderickHyman/albiondata-client/releases)

### Where Can I View The Data I Upload?
> Note that the client can only upload the market orders that you load in game, so be sure to browse the market for the prices that you need. When a price is uploaded, it is visible in the data immediately.

The best way to make use of the data is by using the tools that are built on it:

- [Tools4Albion](https://www.tools4albion.com) provides calculators for crafting, farming, and reprocessing. Has a lot of useful information for users and developers alike.
- [AlbionOnline2d](https://www.albiononline2d.com/en/market) pulls the latest information from the database and shows different selling metrics for the Auction Houses.
- [AlbionAssistant](http://albionassistant.com/) utilizes the data to calculate crafting recipe costs and profits.
- [Farm Profit Calculator](http://aofarm.skyline969.ca/) utilizes market data to provide a guide to the best farming options for you based on current prices.
- [Albion Black Market Master](http://albionblackmarketmaster.com/) looks for quick transactions between the Caerleon Market and the Black Market.
- More tools are actively being developed. If you want your project listed here, contact us using the info below.

Market data can be also be obtained through the API, which has [Swagger documentation available here](https://www.albion-online-data.com/api/swagger). (Item IDs can be found in the [formatted metadata](https://github.com/broderickhyman/ao-bin-dumps/tree/master/formatted), for use in the API.)

> For any of the following urls, .json is optional and is the default, and .json can be replaced with .xml for xml

- Current Prices (Table View): [`https://www.albion-online-data.com/api/v2/stats/view/T4_BAG,T5_BAG?locations=Caerleon,Bridgewatch&qualities=2`](https://www.albion-online-data.com/api/v2/stats/view/T4_BAG,T5_BAG?locations=Caerleon,Bridgewatch&qualities=2)
- Current Prices (JSON): [`https://www.albion-online-data.com/api/v2/stats/prices/T4_BAG,T5_BAG.json?locations=Caerleon,Bridgewatch&qualities=2`](https://www.albion-online-data.com/api/v2/stats/prices/T4_BAG,T5_BAG?locations=Caerleon,Bridgewatch&qualities=2)
- Historical Prices (sell orders only):
  - **New!** [`https://www.albion-online-data.com/api/v2/stats/history/T4_BAG,T5_BAG.json?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6`](https://www.albion-online-data.com/api/v2/stats/history/T4_BAG?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6)
  - **New!** Hourly (time-scale=1): [`https://www.albion-online-data.com/api/v2/stats/history/T4_BAG,T5_BAG.json?time-scale=1`](https://www.albion-online-data.com/api/v2/stats/history/T4_BAG?time-scale=1)
  - **New!** Daily (time-scale=24): [`https://www.albion-online-data.com/api/v2/stats/history/T4_BAG,T5_BAG.json?time-scale=24`](https://www.albion-online-data.com/api/v2/stats/history/T4_BAG?time-scale=24)
  - **New!** For charts: [`https://www.albion-online-data.com/api/v2/stats/charts/T4_BAG,T5_BAG.json?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6`](https://www.albion-online-data.com/api/v2/stats/charts/T4_BAG?date=2-5-2020&end_date=2-12-2020&locations=Caerleon&qualities=2&time-scale=6)
- Gold Prices:
  - **New!** Over time: [`https://www.albion-online-data.com/api/v2/stats/gold.json?date=2-5-2020&end_date=2-12-2020`](https://www.albion-online-data.com/api/v2/stats/gold?date=2-5-2020&end_date=2-12-2020)
  - **New!** Most recent X prices: [`https://www.albion-online-data.com/api/v2/stats/gold.json?count=2`](https://www.albion-online-data.com/api/v2/stats/gold?count=2)
  
Many people find it useful to load these APIs in spreadsheets such as Microsoft Excel or Google Sheets. There is no single best way to do this, but some of the common ways are as follows:

- [Excel Power Query](https://support.office.com/en-us/article/introduction-to-microsoft-power-query-for-excel-6e92e2f4-2079-4e1f-bad5-89f6269cd605)
- [Google Sheets IMPORTXML](https://support.google.com/docs/answer/3093342?hl=en)
> Example: `=IMPORTXML("https://www.albion-online-data.com/api/v2/stats/prices/T4_BAG.xml?locations=Caerleon&qualities=2","//ArrayOfMarketResponse/MarketResponse")`

- [Google Sheets ImportJSON (third-party script)](https://github.com/bradjasper/ImportJSON)
> Note: Some people have noticed issues with ImportJSON and repeating rows

> Example: `=ImportJSON("https://www.albion-online-data.com/api/v2/stats/prices/T4_BAG.json?locations=Caerleon&qualities=2", "", "noHeaders")`

### Related Albion Tools
- [Albion Online Stats - DPS tracker](https://github.com/mazurwiktor/albion-online-stats)

### Configuration
You can see all of the current available command line parameters by launching the executable with `"C:\Program Files\Albion Data Client\albiondata-client.exe" -h` or by adding `-h` to the shortcut.
#### Parameters
At the time of writing the following are the available (well-supported) configuration options:
```
"C:\Program Files\Albion Data Client\albiondata-client.exe" -h
  -d    If specified no attempts will be made to upload data to remote server.
  -debug
        Enable debug logging.
  -events string
        Whitelist of event IDs to output messages when debugging. Comma separated.
  -events-ignore string
        Blacklist of event IDs to hide messages when debugging. Comma separated.
  -i string
        Base URL to send PUBLIC data to, can be 'nats://', 'http://' or 'noop' and can have multiple uploaders. Comma separated. (default "nats://public:thenewalbiondata@www.albion-online-data.com:4222")
  -ignore-decode-errors
        Ignore the decoding errors when debugging
  -l string
        Listen on this comma separated devices instead of all available
  -minimize
        Automatically minimize the window.
  -o string
        Parses a local file instead of checking albion ports.
  -operations string
        Whitelist of operation IDs to output messages when debugging. Comma separated.
  -operations-ignore string
        Blacklist of operation IDs to hide messages when debugging. Comma separated.
  -p string
        Base URL to send PRIVATE data to, can be 'nats://', 'http://' or 'noop' and can have multiple uploaders. Comma separated.
```

#### Disable Start With Windows
1. Open up the program `Task Scheduler`.
1. Click on the `Task Scheduler Library` in the left side pane.
1. Find the task with the name `Albion Data Client`.
1. Right-click `Disable` to disable the task.

### Troubleshooting
Starting the client via the command line will allow the error message to persist. For windows do: `"C:\Program Files\Albion Data Client\albiondata-client.exe"` in the Command Prompt.

#### Client crashing
- "No such device exists" error
  - Go to your internet details and find the Physical Address (MAC Address) for your internet connection. It will look something like `A0-A0-A0-A0-A0-A0`.
  - Then start the client like `"C:\Program Files\Albion Data Client\albiondata-client.exe" -l "A0-A0-A0-A0-A0-A0"` and it should listen to only the interface that you specified.

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

### Database Table Exports

You can find daily table dumps on the server at [https://www.albion-online-data.com/database/](https://www.albion-online-data.com/database/). The export contains a .sql file for each table, and a .zip file for each table that contains a tab-separated .txt data file which can be imported into MySQL using common tools.

### Albion Data Projects
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
