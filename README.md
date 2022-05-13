Hi.

This is a simple high input impedance preamp.  I use it behind a
piezo transducer (MK1) that is repurposed as a hydrophone.  This
circuit can be made on a breadboard if desired.

Many preamp circuits are possible, but I needed one that had the
high input impedance for the piezo unit, and that would take a power
supply as low as 3.3V (it will happily take 5V too).  An alternative
would have been to use MCP6002, or other CMOS opamps, but the
circuit would not be any simpler.  So I went with a discrete JFET amp.

It's important that Q1 be a 2SK117-GR if you need to power the
preamp at 3.3V.  the -BL binned ones have a much higher bias point.
The 2SK117 is typically used in electret condenser mics; any JFET
used in electret condensers will work.

Q2 can be any small signal PNP.  The schematic shows an SMD version,
but the through-hole 2N3906 will be just fine.

R1 should be kept in the megohms, it determines the input impedance.
R5/R3 controls the gain, as shown the gain is about 130 which is
close to the max practical gain.  You can increase R3 to reduce the
gain, but you shouldn't change the R5 value too much. C1||C3 is
quite a large value, in order to retain low frequency response.  If
you aren't interested in low frequencies then you can use a lower
value like 4.uF electrolytic, and you won't need to parallel in a
ceramic cap.  As usual, you should decouple the supply input with
the largest cap (C2) you can afford that is appropriate to the kind
of supply you'll be using.

The preamp is not capacitively coupled!  So the output voltage
with no input (e.g. without the piezo unit connected) should be
around mid supply (1.65V with a 3.3V supply), but this will vary a
lot depending on the specific JFET characteristics.  It's not a
problem as long as it's at least a couple of hundred mV away from
the rails.  To move this Q-point you can change the value of R2 by
up to a factor of 2 up (to move the Q-point up) or down.

There is no output capacitor.  For some applications this is ok, but
add one if you're not certain.  Something like 0.1-10uF will be ok.

