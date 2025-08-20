# Data Files Documentation

This directory contains essential computational data files for the EMDA holographic quantum phase transition analysis.

## File Descriptions

### `eom`
**Equations of Motion**
- Contains the five coupled differential equations for bulk fields {U[z], V1[z], V2[z], a[z], φ[z]}
- Pre-computed from Einstein-Maxwell-Dilaton-Axion (EMDA) action
- Used as: `eom = <<"eom"`
- Format: Wolfram Mathematica expression list

### `BG` 
**Background Solutions**
- Background field solutions in {Tlist, klist} format
- Contains numerical solutions for critical parameter values
- Temperature-chemical potential relationship: `Tlist = (12 - μ²)/(16π μ)`
- Critical k-values: `klist := {147/395, 339/790, 192/395}`
- Format: Nested list structure `{Tlist, klist, field_solutions}`

### `dBG`
**Background Derivatives** 
- Derivatives of background solutions with respect to coordinate z
- Essential for boundary analysis and holographic renormalization
- Used in conjunction with BG for perturbative calculations
- Format: Derivative expressions corresponding to BG structure

### `deomall`
**Complete EOM Dataset**
- Comprehensive equations of motion with all derivative terms
- Includes higher-order corrections and boundary terms
- Used for precision analysis and convergence checks
- Format: Extended equation set with symbolic derivatives

## Usage Notes

- All files are in Wolfram Mathematica binary format
- Load using: `data = <<"filename"`
- Ensure proper directory setup: `SetDirectory[Directory[]]`
- Files are interdependent - load in sequence as needed

## Physical Context

These data files represent the core computational infrastructure for studying quantum phase transitions in the UV region of holographic systems. The background solutions correspond to critical points where quantum phase transitions occur, identifiable through extrema in UV observables rather than traditional IR methods.

## Precision Requirements

All numerical data maintains precision to at least 3 MachinePrecision  for reliable detection of critical behavior signatures in UV observables.
