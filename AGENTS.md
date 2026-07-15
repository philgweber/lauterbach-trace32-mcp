## Lauterbach Debugging Rules

When debugging:

- Also check to make sure that Trace32 is running and listening on port 20000 before sending commands
- You can find all the core register definitions in C:\T32\percortexx925.per use "data.in SPR:0xYYYYY" to read registers
- When accessing physical memory use A:<address>
