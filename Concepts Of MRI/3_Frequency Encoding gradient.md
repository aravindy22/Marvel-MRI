# Frequency Encoding gradient

The frequency encoding gradient is the gradient applied during signal readout that causes spins at different spatial locations to precess at different frequencies, allowing position to be encoded along one image axis.

## How it works

1️⃣ After slice selection and phase encoding,
2️⃣ Frequency encoding gradient (Gx) is switched ON during signal acquisition,
3️⃣ Magnetic field varies linearly along x-direction: B(x)=B0​+Gx​x
4️⃣ Therefore, spins precess at different frequencies:f(x)=γ(B0​+Gx​x)
Each x-position produces a unique frequency in the received signal.

## Signal interpretation

The MR signal is a sum of many frequencies

Fourier Transform separates these frequencies

Each frequency is mapped back to a spatial location

➡ This produces one line of the image per readout.

## Key characteristics

| Feature             | Frequency Encoding        |
| ------------------- | ------------------------- |
| Also called         | Readout gradient          |
| Applied when        | During signal acquisition |
| Encodes position by | Frequency differences     |
| Gradient direction  | X-axis (commonly)         |
| k-space direction   | Horizontal (kx)           |
| Sampling            | Continuous                |

## Frequency vs Phase Encoding
| Aspect             | Frequency Encoding      | Phase Encoding             |
| ------------------ | ----------------------- | -------------------------- |
| Encoding method    | Frequency difference    | Phase difference           |
| Gradient timing    | During readout          | Brief pulse before readout |
| Gradient variation | Constant during readout | Stepped each TR            |
| Motion artifact    | Along phase direction   | More sensitive             |
| k-space            | kx direction            | ky direction               |

## Simple analogy
Imagine:
A piano keyboard
Each key plays a different note (frequency)
You hear all notes together and separate them later

That separation = frequency encoding

## Summary 
Frequency encoding gradient is applied during signal readout to encode spatial position by frequency.

It is also known as the readout gradient.

Fourier transform converts frequency information into spatial location.