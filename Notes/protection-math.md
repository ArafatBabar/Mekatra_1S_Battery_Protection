# Protection Math (Simplified)

Over-current detection is based on:

I_trip ≈ V_threshold / RDS(on)_total

Where:
- V_threshold is the internal detection voltage of the BQ29700
- RDS(on)_total is the combined resistance of the back-to-back MOSFETs

This means protection current depends directly on MOSFET characteristics and temperature.

The absence of a discrete shunt makes this relationship explicit and central to the design.
