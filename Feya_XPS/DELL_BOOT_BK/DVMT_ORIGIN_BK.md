
### DVMT Pre-allocation

| Variable              | Offset | Default value  | Desired value   | Comment                                                    |
|-----------------------|--------|----------------|-----------------|------------------------------------------------------------|
| CFG Lock              | 0x4de  | 0x01 (Enabled) | 0x00 (Disabled) | Disable CFG Lock to prevent MSR 0x02 errors on boot        |
| DVMT Pre-allocation   | 0x785  | 0x01 (32M)     | 0x06 (192M)     | Increase DVMT pre-allocated size to 192M for QHD+ displays |
| DVMT Total Gfx Memory | 0x786  | 0x01 (128M)    | 0x03 (MAX)      | Increase total gfx memory limit to maximum                 |


### Undervolting

 - Overclock, CFG, WDT & XTU enable
 ```BASH
        setup_var 0x4DE 0x00     // (Origin: `0x01`)  
        setup_var 0x64D 0x01     // (Origin: `0x00`)  
        setup_var 0x64E 0x01     // (Origin: `0x00`)  
 ```
 - Undervolting values:
 ```BASH
        setup_var 0x653 0x64     // CPU: -100 mV  (Origin: `0x00`)  
        setup_var 0x655 0x01     // Negative voltage for 0x653  (Origin: `0x00`)  
        setup_var 0x85A 0x1E     // GPU: -30 mV  (Origin: `0x00`)  
        setup_var 0x85C 0x01     // Negative voltage for 0x85A  (Origin: `0x00`)  
 ```      
        
