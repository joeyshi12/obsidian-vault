- 10000 RPM
- 4 platters
- 2 surfaces / platter
- 4096 byte sectors
- 3 ms average seek time
- 1 ms single-track seek time
- 64 sectors / track

**Assume we are writing a 1GB file**

1) Blocks are scattered randomly on disk
2) Blocks are allocated contiguously on a single surface
3) The blocks are allocated contiguously within as few adjacent cylinders as are required to hold all the data. That is, you fill up 1 cylinder at a time

```
1)
f = 60000ms / 10000rot = 6 ms/rot
avgRot = 3 ms
numSectors = 2^30 / 2^12 = 2^18

(seek + avgRot + sectorsRot) * numSectors
ANS = (3 + 3 + 6/64) * 2^18 = 1597440 ms = 26.624 min


2)
numTracks = numSectors / 2^6 = 2^12

avgSeek - sinSeek + (sinSeek + fullRot) * numTracks
ANS = 3 - 1 + (1 + 6) * 2^12 = 28674 ms = 28.674 seconds


3)
numCylinders = numTracks / (4 * 2) = 2^9

avgSeek - sinSeek + (sinSeek + 8*fullRot) * numCylinders
ANS = 3 - 1 + (1 + 8*6) * 2^9 = 25090 ms = 25.090 seconds
```