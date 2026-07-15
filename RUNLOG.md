#Experiment Log:

Expt1: Profile: A.json 
dela_ms: 60ms
Miss: 0.73%
Overhead: 1.98x
Change: initial implempented hybrid FEC+AQr 60ms is min safe delay for max 40 jitter + 20ms FEC offset

Expt2: Profile: B.json
delay_ms: 85ms
Miss: 3.27%
Overhead: 1.98x 
Change: Increase delay 85ms for max jitter 80ms + 20ms FEC buffer but still high miss rate so increased delay more 

Expt3: Profile: B.json
delay_ms: 100ms
frames               : 1500
deadline misses      : 11  (0.73%)   [cap 1.00%]
playout delay        : 100 ms   <-- your score if valid; lower wins
bandwidth overhead   : 1.98x   [cap 2.00x]   (up 472857B, feedback 2872B)
RESULT               : VALID

Expt4: Profile: B.json
delay_ms: 99
frames               : 1500
deadline misses      : 11  (0.73%)   [cap 1.00%]
playout delay        : 99 ms   <-- your score if valid; lower wins
bandwidth overhead   : 1.98x   [cap 2.00x]   (up 472857B, feedback 2872B)
RESULT               : VALID

Expt5: Profile: B.json
delay_ms: 95
frames               : 1500
deadline misses      : 15  (1.00%)   [cap 1.00%]
playout delay        : 95 ms   <-- your score if valid; lower wins
bandwidth overhead   : 1.98x   [cap 2.00x]   (up 472857B, feedback 2872B)
RESULT               : VALID


Expt5: Profile: B.json
delay_ms: 94
frames               : 1500
deadline misses      : 15  (1.00%)   [cap 1.00%]
playout delay        : 94 ms   <-- your score if valid; lower wins
bandwidth overhead   : 1.98x   [cap 2.00x]   (up 472857B, feedback 2872B)
RESULT               : INVALID

Final Lock in: 95 ms (playout delay)
