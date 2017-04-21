
**Reverse engineering Pergo Quickheat wireless kit**![Quickheat controller](./images/controller.jpg?raw=true "Quickheat controller")Examining the frequency using a low-cost SDR and gqrx, shows that the controller communicates on the 868 MHz band. It also gives the following assumptions:-	Static preamble-	No encryption-	Manchester line coding?
-  ASK or *FSK modulation![SDR](./images/pq_data.png?raw=true "SDR data")Next step, finding a suitable low-cost 868 MHz RF transceiver which supports different modulation.-	SI4463 -	CC1101...

...

**Communication**
Current results from sniffing to the communication between sender and receiver using CC1101.GFSK w/Manchester

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


