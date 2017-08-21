---
layout: default
---
Welcome to the Albion Data Project!

The goal of this project is to collect and distribute realtime information for Albion Online. This is achieved with a downloadable client that monitors network traffic specifically for Albion Online, identifies the relevant information, and then ships it off to a central server which distributes the information to anyone who wants it.

### Developer Information
If you're building something to consume the data published by the
Albion Data Project here are some things you will need to know:
- NATS Connection String: nats://public:notsecure@ingest.albion-data.com:4222
- NATS Topics:
  - goldprices.deduped
  - marketorders.deduped
- Structure of data messages: [albiondata-client/lib](https://github.com/Regner/albiondata-client/tree/master/lib)

A note on duplicate messages. As information comes into the NATS Server it is looked at and deduplicated over a 5 minute window. As a subscriber the goal is that you should only get the same message once every 5 minutes. This is of course open for change as we go however. The reason we are sending the same message at all is two fold.
 
New people connecting to the network may have missed previous messages. Along with that however we don’t have a good way of noticing things like market orders completing. To remove market orders from your application the current best idea around is to keep track of the last time an order was seen, and then after not seeing it for X hours remove it as probably having been completed.

### Related Projects
- [albiondata-client](https://github.com/Regner/albiondata-client)
- [albiondata-deduper](https://github.com/Regner/albiondata-deduper)

### Contact Us
The best way to get in touch with us is on the Albion Online Fansites Discord server in either the #proj-albionmarket or the #developers channel. A permanent invite link can be found [here](https://discord.gg/8DDSjTs).
