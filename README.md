# Apple IIc Logic Draw Simulator

This repository is a preservation / reconstruction project for an Apple IIc Applesoft BASIC logic-gate drawing and simulation program originally written from a paper printout from the late 1980s / early 1990s.

The program appears to support:

- Drawing logic gates on an Apple II high-resolution graphics grid
- Connecting gates by numbered line IDs
- Saving and loading circuit data
- Simulating logic levels through gates
- Displaying output states using Apple II shape-table graphics

## Current source

The current recovered listing is in:

- `source/LOGDRW_ANNOTATED.BAS`

This file includes `REM` comments added during recovery to mark the major routines and make the old Applesoft BASIC structure easier to follow.

## Important note about shapes

The original program loads a shape table named `LOGSYB` at address `$0300`:

```basic
20 PRINT CHR$ (4): "BLOAD LOGSYB,A$300"
```

That shape-table binary is not currently available, so the exact gate symbols, digits, inversion bubbles, and display marks are still missing. The BASIC source shows where those shapes are used through `DRAW` and `XDRAW` statements, but not the shape data itself.

## Major recovered sections

- Startup / shape-table load
- Main menu dispatch
- Gate / symbol entry
- Load circuit
- Save circuit
- Show / simulate circuit
- Line menu and disconnect/reconnect handling
- Screen/grid drawing
- Menu drawing
- Find gates connected to a line
- Check for occupied grid location
- Clear temporary line state
- Delete temporary gate data
- Draw input line
- Draw connection between gates
- Draw output line
- Reconnect disconnected line

## Status

This is a recovered listing and may still contain transcription errors. The goal is to preserve the original Apple II logic first, then later use it as a reference for a modern rewrite or emulator-based restoration.
