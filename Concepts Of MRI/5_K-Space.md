# K-Space

k-space is the raw data space in MRI where the scanner stores signals before an image is formed.

👉 It is not an image
👉 It is a map of spatial frequencies

## What is stored in k-space

- Each point contains information about all parts of the image

- Data is filled line by line

- One line is collected in one TR

## How k-space is filled

- Phase encoding gradient chooses the line (ky)

- Frequency encoding gradient fills the line (kx)

- Repeating this fills the whole k-space


## Center vs edges of k-space
| Region | Controls                 |
| ------ | ------------------------ |
| Center | Image contrast & signal  |
| Edges  | Image detail & sharpness |


## How image is formed

After k-space is fully filled:

- Fourier Transform is applied

- k-space → image space

📌 Without Fourier Transform, k-space has no visual meaning

##

0️⃣ First: what k-space really is (mental reset)

k-space is NOT an image

It is a storage space for spatial frequency information

Every point in k-space affects every pixel in the image

Think of k-space as a recipe, not the food.

1️⃣ One TR = one horizontal line in k-space

During one repetition (TR):

Slice is excited

Phase encoding gradient is applied

Frequency encoding gradient is turned ON

Signal is collected

👉 That single signal readout fills one horizontal line in k-space.

📌 You never fill a dot — you fill a line

2️⃣ Why phase encoding decides which line

Phase encoding gradient strength determines:

Which ky value you are filling

Stronger gradient → farther from center

Weaker gradient → closer to center

So:

Each TR uses a different phase encoding strength

Each strength maps to a different k-space line

3️⃣ Start at the center (ky = 0)

When phase encoding = 0:

All spins have the same phase

This fills the center line of k-space

What does center mean?

Low spatial frequencies

Image contrast

Overall brightness

📌 If you lose center k-space → image contrast is lost

4️⃣ Move outward line by line

Next TRs:

Slight + phase encoding → ky = +1

Slight − phase encoding → ky = −1

Larger + → ky = +2

Larger − → ky = −2

…

This continues until:

Entire ky range is filled

Think of painting:

Start with the broad background

Then add finer details

5️⃣ What frequency encoding does inside a line

While filling one ky line:

Frequency encoding gradient changes position → frequency

Fourier Transform along this direction fills kx

So:

kx is filled continuously

ky is filled step-by-step

6️⃣ Why edges of k-space matter
k-space region	Image effect
Center	Contrast, signal strength
Outer edges	Sharpness, fine detail

This is why:

Motion during center filling → severe artifacts

Truncation of edges → blurred image

7️⃣ Acquisition order matters

MRI does NOT have to fill k-space sequentially.

Common strategies:

Linear (center halfway through scan)

Centric (center first)

Reverse centric

Spiral / radial

Each choice affects:

Motion sensitivity

Contrast timing

Artifact behavior

8️⃣ Final step: image appears

After k-space is full:

2D Fourier Transform is applied

k-space → image space

Contrast + detail emerge together

📌 No single k-space line equals one image row — it’s collective.

## Summary

k-space is the frequency-domain storage of MRI data that is mathematically transformed into an image.

k-space is filled one line per TR, controlled by phase encoding; the center controls contrast, edges control detail; the image appears only after all data is combined.

# How patient Motion effects K-space (Important)

MRI assumes the patient stays still while k-space is being filled line by line.
When the patient moves, different k-space lines no longer match the same anatomy, so the final image becomes distorted.

1️⃣ Remember how k-space is built

One TR = one k-space line

Each line is collected at a different time

The image is reconstructed only after all lines are combined

👉 Motion = anatomy changes between lines

2️⃣ What motion actually does to k-space
🧠 Case A: No motion

Every k-space line comes from the same anatomy

Lines fit together perfectly

Clean image after Fourier Transform

🧠 Case B: Patient moves during scan

Some k-space lines come from position A

Others come from position B

k-space becomes inconsistent / corrupted

📌 k-space now contains mixed spatial information

3️⃣ Why motion mostly causes ghosting

Motion mainly affects phase encoding

Phase encoding happens:

Briefly

Differently each TR

Motion changes the stored phase pattern

👉 Result after reconstruction:

Repeated faint copies (ghosts) along the phase-encoding direction

4️⃣ Why center k-space motion is worse
| k-space region | Motion effect              |
| -------------- | -------------------------- |
| Center         | Severe contrast distortion |
| Outer edges    | Mild blurring              |

📌 If patient moves while center of k-space is being filled:

Entire image contrast is damaged

Artifacts become very prominent

5️⃣ Types of motion & their k-space effects
🚶 Voluntary motion (head, body)

Sudden phase jumps

Strong ghosting

❤️ Physiological motion (breathing, heartbeat)

Periodic phase errors

Repetitive ghost patterns

🩸 Flow (blood, CSF)

Phase shifts → signal loss or ghosting

6️⃣ Why frequency encoding is less affected

Frequency encoding happens during one readout

Motion during that short time mainly causes slight blurring

Phase encoding errors accumulate across TRs → much worse

## Summary
Patient motion causes k-space inconsistency; phase errors between lines lead to ghosting and blur after Fourier Transform. 

# Fourier Transform
The inverse Fourier Transform mathematically converts k-space frequency data into spatial pixel intensities by combining all encoded frequencies and phases.

1️⃣ What a pixel represents

A pixel at position (x, y) is a single number (intensity) that answers:

“How much signal comes from this location?”

But MRI never measures that directly.

2️⃣ What k-space actually stores

k-space is a grid of complex samples indexed by (kx, ky).

Each sample contains global information about the whole slice.

No k-space point belongs to one pixel.

3️⃣ The key rule (this is the heart of it)

Every pixel is computed using all k-space points.

4️⃣ What the “weight” really means (intuition)

Each k-space point represents a spatial wave pattern:

Low k (near center) → slow, smooth waves

High k (edges) → fast, fine-detail waves

To build a pixel at (x, y):

MRI adds all these waves

At that location, some waves add up

Others cancel out

👉 The final sum = pixel intensity

5️⃣ Why center vs edge of k-space matter
k-space region	Effect on pixel
Center	Sets overall brightness & contrast
Outer edges	Sharpen edges & fine detail

So if:

You change center k-space → pixel brightness changes

You remove edge k-space → pixel becomes blurry

6️⃣ Step-by-step mental picture

Each k-space point says:
“Add a faint ripple pattern across the image.”

Fourier Transform stacks all ripple patterns

At each pixel:

Ripples interfere

Constructive → bright

Destructive → dark

📌 A pixel is interference of all k-space information.

7️⃣ Why this feels unintuitive (and that’s OK)

We expect:

“One measurement → one pixel”

MRI does:

“All measurements → every pixel”

That’s why:

Motion corrupts many pixels

Partial k-space affects the whole image

8️⃣ Ultra-simple analogy (lock this in)

🎵 Music analogy

Each k-space point = one musical note pattern

Pixel = loudness at a seat in the hall

Loudness depends on all notes together


```
A pixel is not read from k-space; it is constructed by summing contributions from every k-space sample during the inverse Fourier Transform.
```

## 
1️⃣ The simplest possible MRI “image”

Assume the true image (what we want to recover) is a 2×2 slice:

Image (real space)
┌───────┬───────┐
│  A    │  B    │
├───────┼───────┤
│  C    │  D    │
└───────┴───────┘

Each letter is a pixel intensity.

2️⃣ Corresponding k-space (what MRI actually measures)

For a 2×2 image, k-space is also 2×2:

k-space
┌────────┬────────┐
│ K00    │ K01    │
├────────┼────────┤
│ K10    │ K11    │
└────────┴────────┘
**Each K is a complex number (amplitude + phase).**

3️⃣ Relationship between k-space and image (key idea)

Each k-space value is a mixture of ALL pixels.

For a 2×2 case, the inverse Fourier transform boils down to adding and subtracting.

4️⃣ Inverse Fourier Transform rules (2×2 case)

The pixels are reconstructed like this:

A = ( K00 + K01 + K10 + K11 ) / 4
B = ( K00 - K01 + K10 - K11 ) / 4
C = ( K00 + K01 - K10 - K11 ) / 4
D = ( K00 - K01 - K10 + K11 ) / 4
👉 Every pixel uses ALL k-space points

5️⃣ Plug in actual numbers (real example)

Assume MRI measured:

K00 = 40   (center of k-space)
K01 = 10
K10 = 6
K11 = 4

6️⃣ Reconstruct each pixel
Pixel A
A = (40 + 10 + 6 + 4) / 4
A = 60 / 4 = 15

Pixel B
B = (40 - 10 + 6 - 4) / 4
B = 32 / 4 = 8

Pixel C
C = (40 + 10 - 6 - 4) / 4
C = 40 / 4 = 10

Pixel D
D = (40 - 10 - 6 + 4) / 4
D = 28 / 4 = 7

7️⃣ Final reconstructed image

Image
┌───────┬───────┐
│ 15    │  8    │
├───────┼───────┤
│ 10    │  7    │
└───────┴───────┘

🎉 The image has appeared — only after combining all k-space values.

8️⃣ Why this example is powerful

From this tiny example you can clearly see:

✅ One k-space point ≠ one pixel
✅ Every pixel depends on all k-space data
✅ Changing K00 (center) affects all pixels strongly
✅ Changing edge terms affects contrast between pixels

9️⃣ Key intuition to keep forever

k-space values are global measurements;
pixels are local results formed by interference of all measurements.

## Summary

In MRI, a pixel is constructed by summing weighted contributions from every k-space sample via the inverse Fourier Transform.