# Bloomburgular -- the super micro fun implant


## Goals of the implant

The design of the implant had the following constraints:

- Could occur during the supply chain OR after customer has taken
  receipt of the drive (think red team or insider threat)
- Requires zero firmware
- Fits inside the Nano S
- Bypasses a core security function
- Few components (cheap and DIY)
- FUN to build and use (not bluetooth)

## Theory of Operation

When the selected RF signal is detected, the output is pulled low.

That's it.

## Parts:

- C1: DC Blocking CAP
- R3: Pot for voltage adjustment (see notes below)
- Q1: NPN Transistor
- R1: Bias resistor
- R2 & C2: Low pass filter

## Operating Tips

The only thing tuning this circuit is the antenna. Experiment with
different antennas for different frequencies! We used 17cm for decent
reception at 433MHz. At 433Mhz, we had a 50W transmitter around so
that was fun :)

For the pot, you can make your circuit more or less sensitive. We
adjusted ours so that the output (GPIO) came down to about 2.9V. If
the pot is too low, you'll need a strong signal and too high, it will
pull the GPIO low without any RF.

## Improvements

You can remove the put and put in your own voltage divider and that
will save 80 percent of the BoM. Worse case, you will have to tune by
reworking SMD resistors, which isn't so bad.
