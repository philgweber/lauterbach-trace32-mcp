---
name: memory-triage
description: >
  Use this skill to inspect MMU and memory state of device through Trace32
---

# Memory Triage Skill

## Goal

Help the user triage MMU and memory state information through Trace32

## Activation Guidance

Use this skill when the user asks about:

- MMU state inspection
- Memory layout analysis
- Physical memory access patterns
- Virtual memory management
- Cache behavior and coherency
- Memory controller status
- DRAM timing and configuration

## Required Behavior

When dumping memory information:

1. Make sure sys.option.dbgspr on is set in Trace32
2. Check the current PSTATE and exception level to determine which TTBR register to use for table walks.
3. Make sure Trace32 is connected to the target device and can be halted.
4. Make sure the general purpose registers and MMU state can be read.
5. When looking up memory mappings, use physical memory and TTBR registers to do the table walk.

## Trace32 Commands to use

Prefer commands like:

```text
data.in A:<PhysicalAddress> /quad
data.in SPR:0xYYYYY
