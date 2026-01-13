# 1S Li-Ion BMS (BQ29700)

This repository contains a reference 1S battery protection design built around the Texas Instruments BQ29700 single-cell protection IC.

The design targets single-cell Li-ion packs (including parallel configurations such as 1S3P) and follows TI’s intended protection architecture using external back-to-back MOSFETs.

---

## Overview

Key characteristics of this BMS:

- Single-cell Li-ion protection (1S)
- Over-voltage and under-voltage protection
- Over-current and short-circuit protection
- No dedicated current sense resistor
- Over-current detection via MOSFET RDS(on) sensing
- Back-to-back N-channel MOSFET topology
- Conservative, safety-biased protection behavior

The protection thresholds are defined by the MOSFET characteristics and the internal voltage detection of the BQ29700, rather than by a discrete shunt.

---

## Core Components

- **Protection IC:** TI BQ29700
- **MOSFETs:** CSD16406Q3 (datasheet-recommended, back-to-back)
- **Cell configuration:** 1S (supports parallel cells, e.g. 1S2P / 1S3P)
- **Intended use:** Portable electronics, power banks, embedded battery systems

---

## Current Sensing Approach

Unlike many BMS designs that rely on a low-value shunt resistor, this implementation uses the MOSFETs themselves as the current-sensing element.

Over-current detection is performed by monitoring the voltage drop between BAT and V−, which corresponds to:

