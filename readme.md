
**Reverse engineering Pergo Quickheat wireless kit**
-  ASK or *FSK modulation

...

**Communication**


**TX packet**

| Byte # | Data        | Comment  |
|:--:|:------------- |:-------- |
| 0  |               |          |
| 1  |               |          |
| 2  |               |          |
| 3  |               |          |
| 4  | command?<br>[7:2] - ?<br>[1] - frost protection on/off <br>[0] - set/check floor temp. | |
| 5  |               |          |
| 6  | [7:0] - address? | |
| 7  |               |          |
| 8  | [7:0] - set floor temperature | byte * 0.5 = C          |
| 9  |               |          |
| 10 |               |          |
| 11 | [1] - frost protection config? | |
| 12 | [7:5] - frost protection config? | |
| 13 |               |          |


**RX packet**

| Byte # | Data      | Comment  |
|:------:|:--------- |:-------- |
| 0  |               |          |
| 1  |               |          |
| 2  |               |          |
| 3  |               |          |
| 4  |               |          |
| 5  | [7:0] - current floor temperature | (byte - 80) * 0.5 = C|
| 6  |               |          |
| 7  |               |          |
| 8  |               |          |

