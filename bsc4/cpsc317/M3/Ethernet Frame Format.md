![[Ethernet Frame Format 2022-10-11 10.59.04.excalidraw|700]]

| Component                 | Bytes | Description                                     |
| ------------------------- | ----- | ----------------------------------------------- |
| Preamble                  | 8     | ...                                             |
| Destination address (MAC) | 6     | Hardware address of destination network adapter |
| Source address (MAC)      | 6     | Hardware address of the source network adapter  |
| Type                      | 2     | Ethernet 2 layer 3 label                        |
| CRC                       | 6     | Error detection                                 |
