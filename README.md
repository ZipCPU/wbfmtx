# A Wishbone Controlled FM Transmitter Hack

This Hack is based off of two things: 1) the interface spec of the WB
controlled PWM audio device, and 2) a Raspberry Pi Hack I was shown that
converted the RPi PWM device into an FM transmitter.  So, the question is, can
a GPIO pin be turned into an FM transmitter that can be heard throughout the
house?

The answer is that a GPIO pin can be transformed into an FM transmitter, and
that it then and broadcasts nicely--although weakly.  If I make every
pin a GPIO pin, then I can get perhaps a yard or so from the transmitter device.
The hack also has a newer interface, written but not tested, that outputs
4-samples per clock.  This should provide a rough 10dB boost to the signal
strength since the signa would no longer be undersampled, but I haven't tested
the update yet.  That and an antenna (I never used any antennas) should be
able to provide a nice capability.
