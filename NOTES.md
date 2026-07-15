
The architecture uses a highly optimized hybrid FEC and ARQ strategy that consistently stays under the 2.0x bandwidth cap. We employ a compressed 1-byte header to embed the previous frame's payload (`dup_offset = 1`) into almost every packet. The sender tracks its bandwidth usage dynamically, dropping the duplicate payload only when necessary to maintain strict budget compliance. The receiver unpacks the 7-bit sequence numbers using modular arithmetic against the highest received sequence. To handle rare burst losses, the receiver sends a reverse feedback packet containing an ACK sequence and a 32-bit missing mask. The sender parses this feedback and intelligently substitutes the standard FEC frame for the oldest missing frame when ARQ is needed, giving priority to dropped packets. Crucially, the receiver immediately plays any recovered frame to the harness player to maximize the chance of arriving before the rigid deadline, eliminating the need for a complex jitter buffer timer.


Please grade at --delay_ms 95 ms.

What Breaks It?

The design breaks if the network experiences severe and prolonged burst losses (e.g. dropping more than 5 consecutive packets), which would overwhelm the 32-bit missing mask ARQ window before retransmissions can arrive. It also breaks if maximum network jitter exceeds 100ms, as the dup_offset=1 FEC packets would consistently arrive after the delay_ms = 105 deadline.
