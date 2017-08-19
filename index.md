---
layout: default
---
Welcome to the Albion Data Project!

### Developer Information
If you're building something to consume the data published by the
Albion Data Project here are some things you will need to know:

- NATS Connection String: nats://public:notsecure@ingest.albion-data.com:4222
- NATS Topics:
  - goldprices.deduped
  - marketorders.deduped
- Structure of data messages: [albiondata-client/lib](https://github.com/Regner/albiondata-client/tree/master/lib)

### Related Projects
- [albiondata-client](https://github.com/Regner/albiondata-client)
- [albiondata-deduper](https://github.com/Regner/albiondata-deduper)
