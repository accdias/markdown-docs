# Extracting and Compiling DSDT information on Linux


## Introduction

Here are instructions on how to extract and compile BIOS DSDT information
from Linux systems

## Ingredients

* Flash drive with 1 or 2 gigabytes of capacity
* Computer running Linux

## Instructions

1. Launch a terminal

2. In the terminal, run the following command:

```bash
cat /proc/acpi/dsdt > ~/dsdt.aml
```

3. Mount the flash drive

4. Copy the `dsdt.aml` file to the flash drive

5. Eject the flash drive

6. Boot MacOS OSx86

7. Edit the `dsdt.aml` file using DSDTSE as described in the
previously linked-to Guide.

As usual DSDT editing is an art, not a science, and one is sure to
stumble on some gotchas the first few times.

One solution is to compile the DSDT after every edit, discarding the
results as one goes, until the final edit compiles without error.

Something as simple as a misplaced line-feed or a missing closed curly
brace can be enough to get one the dreaded "parse failed at end-of-
file" message, and a return to the beginning (if incremental compiles
ARE NOT being done) or a return to the immediately preceding edit (if
incremental compiles ARE being done) will be necessary.

