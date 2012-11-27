# Reverse engeenering dumps/6577-readback-0-400.pcap

* When device connected to host it send 120 packets payloaded with 'READY' string.
* Host expect 'READY' and start connection check by sending A0 and expect 5F (inverse of A0)
* Host continue connection check with sending 0A, 50, 05 and expect F5, AF, FA

## Connection check

```
-----------------------
Host        Device
-----------------------
            "READY"
a0          5f
0a          f5
50          af
05          fa
```

## Preloader version check
```
-----------------------
Host        Device
-----------------------
fd          fd
            65 75       # Seems like we has 6575 preloader. WTF? This was captured from 6577 board!
            00 00       # Status code? Revision?
```

### All following may be 6515/6575/6577 specific, because host know preloader type (6575)

To be continued...
