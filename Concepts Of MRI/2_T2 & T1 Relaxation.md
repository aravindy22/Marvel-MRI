# T2 Relaxation 

It also called **spin–spin relaxation** describes how quickly the transverse magnetization (signal in the xy-plane) decays after an RF pulse in MRI.

## What actually happens?

After an RF pulse tips protons into the transverse plane, their spins initially precess in phase.

Due to microscopic interactions between neighboring spins (local magnetic field variations), they gradually lose phase coherence.

As spins dephase, the transverse magnetization decreases → MRI signal fades.

This decay follows an exponential curve characterized by the T2 time.
```
Mxy​(t)=Mxy​(0)e−t/T2​
```

**T2 = time at which transverse magnetization drops to 37% of its initial value.**

## Tissue differences (why images look different)

| Tissue               | T2 Time       | Appearance on T2-weighted MRI |
| -------------------- | ------------- | ----------------------------- |
| CSF / Water          | Long T2       | **Bright**                    |
| Edema / Inflammation | Long T2       | **Bright**                    |
| Gray matter          | Medium T2     | Gray                          |
| White matter         | Shorter T2    | Darker                        |
| Bone / Air           | Very short T2 | Black (no signal)             |


## T2-weighted imaging

To emphasize T2 differences:

- Long TE (Echo Time)

- Long TR (Repetition Time)

This suppresses T1 effects and highlights T2 decay.

## Clinical use:
T2-weighted MRI is excellent for detecting: Edema, Tumors, Infection, Inflammation, Ischemic changes

## T2 vs T2*

T2: True spin–spin relaxation (intrinsic tissue property)

T2*: Includes T2 effects plus magnetic field inhomogeneities

Always shorter than T2

Used in GRE sequences

## Simple analogy

Imagine runners starting together on a track, Over time, they drift apart at different speeds, The group loses synchronization → signal weakens

**That loss of synchronization = T2 relaxation**

# T1 Relaxation

It is also called spin–lattice relaxation) describes how quickly the longitudinal magnetization (Mz) recovers along the main magnetic field (B₀, z-axis) after an RF pulse in MRI.

## What actually happens?

An RF pulse tips the net magnetization away from the z-axis.

Protons then release energy to their surrounding molecular environment (lattice).

As energy is lost, magnetization realigns with B₀, restoring longitudinal magnetization.

The speed of this recovery is tissue-dependent and defined by the T1 time.

```
Mz​(t)=M0​(1−e−t/T1​)
```
**T1 = time at which longitudinal magnetization recovers to 63% of its maximum value (M₀).**

## Tissue differences (key for contrast)

| Tissue       | T1 Time         | Appearance on T1-weighted MRI |
| ------------ | --------------- | ----------------------------- |
| Fat          | Short T1        | **Bright**                    |
| White matter | Short–medium T1 | Light gray                    |
| Gray matter  | Medium T1       | Gray                          |
| CSF / Water  | Long T1         | **Dark**                      |
| Bone / Air   | No signal       | Black                         |


## T1-weighted imaging

To emphasize T1 differences:

Short TR (Repetition Time)

Short TE (Echo Time)

This allows tissues with short T1 to recover faster and appear brighter.

## Clinical use:

T1-weighted MRI is excellent for: Normal anatomy, Fat-containing structures, Post-contrast imaging (Gadolinium shortens T1), Detecting hemorrhage (subacute)

## Effect of contrast agents
Gadolinium reduces T1 relaxation time.

Tissues that take up contrast become brighter on T1-weighted images.

Widely used in tumor detection, inflammation, and vascular imaging.


# T1 vs T2 (Comparison)

| Feature         | T1                | T2               |
| --------------- | ----------------- | ---------------- |
| Magnetization   | Longitudinal (Mz) | Transverse (Mxy) |
| Energy exchange | With lattice      | Between spins    |
| Water signal    | Dark              | Bright           |
| Fat signal      | Bright            | Dark             |
| Best for        | Anatomy           | Pathology        |


# Short Summary 

T1 Relaxation (Spin–Lattice)
Recovery of longitudinal magnetization (Mz) along B₀ due to energy transfer to surrounding lattice.

T2 Relaxation (Spin–Spin)
Decay of transverse magnetization (Mxy) due to loss of phase coherence between spins.

## T1 vs T2 — High-Yield Comparison Table

| Feature                | **T1 Relaxation** | **T2 Relaxation** |
| ---------------------- | ----------------- | ----------------- |
| Also called            | Spin–lattice      | Spin–spin         |
| Magnetization affected | Longitudinal (Mz) | Transverse (Mxy)  |
| Energy exchange        | With surroundings | Between spins     |
| Mechanism              | Energy loss       | Phase loss        |
| Time constant          | Longer            | Shorter           |
| Water signal           | Dark              | Bright            |
| Fat signal             | Bright            | Dark              |
| Sensitivity            | Anatomy           | Pathology         |
| Contrast agent effect  | Strong            | Minimal           |
| Typical sequences      | T1-weighted, IR   | T2-weighted, FSE  |
| Relation               | T1 > T2 always    | T2 < T1 always    |

## Tissue Signal Appearance

| Tissue       | T1 Image | T2 Image     |
| ------------ | -------- | ------------ |
| Fat          | Bright   | Dark         |
| White matter | Bright   | Dark         |
| Gray matter  | Gray     | Lighter gray |
| CSF / Water  | Dark     | Bright       |
| Edema        | Dark     | Bright       |
| Tumor        | Dark/iso | Bright       |

## Imaging Parameters

T1-weighted MRI

- Short TR

- Short TE

T2-weighted MRI

- Long TR

- Long TE

## Clinical Importance

T1 images

- Best for normal anatomy

- Used for post-contrast (Gadolinium) studies

- Detects fat, hemorrhage (subacute)

T2 images

- Best for pathology

- Highlights edema, inflammation, tumors, infarcts


## Memory Trick

T1 = FAT is Bright

T2 = WATER is White

T1 shows structure

T2 shows trouble

T1 relaxation: Recovery of longitudinal magnetization due to energy exchange with lattice.

T2 relaxation: Decay of transverse magnetization due to spin–spin interactions.

Why T2 < T1? Phase loss occurs faster than energy transfer.







