# Design Decisions

## Why no sense resistor?

The BQ29700 supports over-current detection by sensing the voltage drop across external MOSFETs. Using this mechanism avoids introducing an additional shunt resistor in the high-current path.

This reduces power loss and simplifies routing, but requires careful MOSFET selection.

## Why CSD16406Q3?

This MOSFET is explicitly recommended in TI reference designs for the BQ29700. Its RDS(on), SOA, and thermal behavior are well characterized for battery protection use cases.

## Safety bias

Protection thresholds are intentionally conservative. This limits fault energy during short-circuit events and keeps the system within predictable operating boundaries.
