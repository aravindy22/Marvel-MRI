# Phase Encoding Gradient
When the MR signal is received, all spins talk at the same time. We must figure out where each signal came from.

## MRI solves this using gradients:

Slice selection → which slice

Frequency encoding → left–right

**Phase encoding → up–down**

## What “phase” actually means 

A spinning proton behaves like a clock hand.

Two spins can:

- Spin at the same speed (same frequency)

- But point in different directions (different phase)

**Phase = angular position of the spin at a given moment.**

## What the phase encoding gradient does
The phase encoding gradient briefly makes spins at different positions:

- Spin slightly faster or slower

- For a short time only

Because of this:

- Spins at different locations end up with different phase angles

- When the gradient is turned off, frequencies become the same again

- But the phase difference remains stored

👉 **This stored phase is the “position label”.**

## Step 1: All spins start in sync

After RF excitation:

- Spins in the slice rotate together

- Same frequency, same phase

## Step 2: Phase encoding gradient is turned ON (briefly)

Gradient is applied along y-direction

Spins at different y-positions experience slightly different fields

They accumulate different phase shifts

Think of runners on a track:

- Some speed up, some slow down

- After a short time, they are no longer aligned

## Step 3: Phase encoding gradient is turned OFF
All spins return to the same frequency

But their phase offsets remain

**Phase encoding stores position information without continuous gradient**

## Step 4: Readout happens later
Frequency encoding reads the signal

Phase differences are decoded mathematically (Fourier Transform)Frequency encoding reads the signal

Phase differences are decoded mathematically (Fourier Transform)

## Why phase encoding is repeated many times
One phase-encoded signal gives only one projection.

So MRI:

- Repeats the sequence many times

- Each time with a slightly different phase gradient strength

- Gradually fills k-space line by line

Analogy:

- Taking many photos from slightly different vertical shifts

- Later combining them to form a clear image

## Why phase encoding is slow but powerful

Requires many repetitions

Sensitive to motion

But allows:

- High spatial resolution

- Flexible image orientation

- 2D and 3D imaging

## Phase vs Frequency encoding

| Aspect             | Phase Encoding | Frequency Encoding |
| ------------------ | -------------- | ------------------ |
| Gradient duration  | Short, pulsed  | Long, continuous   |
| Stored info        | Phase offset   | Frequency          |
| Repetition         | Many TRs       | One per TR         |
| Motion sensitivity | High           | Lower              |

## Summary 
Phase encoding works by briefly changing spin speeds so they accumulate different phase shifts; those phase shifts store spatial position information.