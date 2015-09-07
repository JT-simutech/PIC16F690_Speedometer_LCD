#PIC-Speedometer

PIC16F690 simple speedometer

    Processor; Microchip microcontroller, PIC16F690
    Project opens with: MPLAB v.8.88
    Compiler used: HITECH PICC compiler

Description; Simple speedometer and odometer for LCD BTHQ 16x2 lines display Uses internal EEPROM onboard uC to store ODO value.

Pin Out(GPIO): *IO: | Function: LCD: *--- ----- ----- ----- ----- ----- ----- ----- *OUTPUTS: *RC0 | Register Select (RS) | "RS" pin 4 *RC1 | Read/Write(R/W) | "R/W" pin 5 *RC2 | Chip Enable (E) | "E" pin 6 *RC4 | Dataline bit 4 (D4) | "D4" pin 11 *RC5 | Dataline bit 5 (D5) | "D5" pin 12 *RC6 | Dataline bit 6 (D6) | "D6" pin 13 *RC7 | Dataline bit 7 (D7) | "D7" pin 14 * *RB7 | Watchdog L.E.D
*------------------------------------------------------------ *INPUTS: *RA2 = T0INT | Counter 0 *RA5 = T1INT | Counter 1 *------------------------------------------------------------ *Details: *Startup, read ODO value from EEPROM (uC internal). * *TIMER0 - ODOMETER: *Counter mode. Pre-load with initial value. *When Timer0(counter) overflows, interrupt occurs and updates ODO every 100 meters. * *TIMER1 - SPEED: *8 bit Counter, auto reload.

    1) Start upon: Pulse from speedo sensor (magnetic switch)
    2) Convert count to time since last sensor pulse * ***************************************************
    //TODO; decide whether the pulse is stale or not. * ***************************************************
    3) Reset TIMER 1, ready to wait for next pulse
    4) //TODO: Valid pulse?
    Convert time since last pulse --> speed using predefined wheel circumference.
    //TODO: Invalid/stale pulse: Reset counter, show 0 Km/h
    5) Update LCD display (slow process..)

    Status API Training Shop Blog About Pricing 

    © 2015 GitHub, Inc. Terms Privacy Security Contact Help 
