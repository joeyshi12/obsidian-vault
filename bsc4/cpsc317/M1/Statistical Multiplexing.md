# Statistical Multiplexing
A sharing technique that allows data from a number of channels to be combined
for transmission over a single transmission line

**Idea**: depends on statistical information about arrival rate of data.
Bandwidth is allocated according to the probability of need

## StatMux != Packet Switching
- Packet switching uses statistical multiplexing at the channel level
- StatMux can be used at higher levels, for instance for allocating circuits
- Packet switching does not imply StatMux **across** channels

## StatMux Cons
- Not good when demand is constant (radio station)
- Not good when demand is dependent (flash crowd)

