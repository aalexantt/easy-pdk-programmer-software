EASY PDK PROGRAMMER
-------------------

Hardware sources can be found here: https://github.com/free-pdk/easy-pdk-programmer-hardware

```
Usage: easypdkprog [OPTION...] list|probe|read|write|erase|start [FILE]
easypdkprog -- read, write and execute programs on PADAUK microcontroller
https://free-pdk.github.io

  -b, --bin                  Binary file output. Default: ihex8
  -f, --fuse=FUSE            FUSE value, e.g. 0x31FD
  -i, --icid=ID              IC ID 12 bit, e.g. 0xAA1
      --noverify             Skip verify after write
      --nocalibrate          Skip calibration after write.
  -n, --icname=NAME          IC name, e.g. PFS154
      --noblankchk           Skip blank check before write
      --noerase              Skip erase before write
  -p, --port=PORT            COM port of programmer. Default: Auto search
  -r, --runvdd=VDD           Voltage for running the IC. Default: 5.0
      --securefill           Fill unused space with 0 (NOP) to prevent readout
  -v, --verbose              Verbose output
  -?, --help                 Give this help list
      --usage                Give a short usage message
  -V, --version              Print program version
```

Examples:

list all supported ICs:
```  easypdkprog list```

probe IC in socket (can determine IC type/name):
```  easypdkprog probe```

read IC to readout.hex file:
```  easypdkprog -n PFS154 read readout.hex```

read IC to readout.bin file:
```  easypdkprog -n PFS154 read readout.hex -b```

write IC:
```  easypdkprog -n PFS154 write myprog.hex```

erase IC (flash based only):
```  easypdkprog -n PFS154 erase```

start IC in socket (interactive mode):
 all serial output sent form IC-PA.7 (autobaud detection) is displayed on screen
 all input from keyboard is sent as serial to IC-PA.0 (using same detected baud as receive)
 
```  easypdkprog start```

  
