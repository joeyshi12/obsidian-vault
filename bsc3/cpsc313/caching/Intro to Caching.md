---
course: "cpsc313"
title: "Introduction to Caching"
lesson: "P12.1"
chapters: [6.2, 6.3]
---


## Definitions
- Application asks for a data item from cache
    - Read Cache HIT: the cache has the data and returns the item
    - Read Cache MISS: cache doesn't have that item, it will ask the data from the data source, and then return it to the application
- Cache Misses
    - Compulsory: on first access to an object, you take a miss; there is little you can do about it
- Capacity:
    - You are touching more data than can fit in the cache.
    - If your cache were larger, you would have fewer misses.
- Conflict:
    - In most caches, there's a limited number of places in the cache in which you can put a particular piece of data.
    - Misses that occur because the particular place (or places) in which a piece of data must go are occupied are called conflict misses

 
## Cache Design Decisions
- Blocksize/Linesize
    - How much data to return?
- Eviction/Replacement Policy
    - What do to when space runs out?
- Cache Organization
    - How do I know what's in the cache?
    - Where do I put things in my cache?
    

## How much data should I return?
- Block size: the unit in which data is stored in a cache.