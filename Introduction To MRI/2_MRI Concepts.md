# Main coil
The main coil produces the strong, static magnetic field called B₀. This field is always ON in superconducting MRI.

- Function of Main Coil

1) Aligns hydrogen protons in the body

2) Creates the base field required for MRI

3) Without this field → MRI cannot work

| Feature        | Value                  |
| -------------- | ---------------------- |
| Field type     | **Static (constant)**  |
| Field strength | **1.5 T, 3 T, 7 T**    |
| Current        | Superconducting        |
| Cooling        | Liquid Helium (−269°C) |
| Always ON?     | ✅ Yes                 |


**Main coil = Creates the magnetic environment for MRI**

# Gradient Coils (Spatial Encoding Coils)

Gradient coils create small, rapidly changing magnetic fields on top of the main magnetic field.

They tell the MRI exactly where the signal is coming from.

| Gradient | Direction    | Purpose            |
| -------- | ------------ | ------------------ |
| **Gx**   | Left ↔ Right | Frequency encoding |
| **Gy**   | Front ↔ Back | Phase encoding     |
| **Gz**   | Head ↔ Foot  | Slice selection    |

- Functions of Gradient Coils

They perform:

✅ Slice selection

✅ Frequency encoding

✅ Phase encoding

**Without gradients → no image formation, only signal.**

✅ Why Gradient Coils Are Noisy?

They switch ON and OFF very fast

This causes strong vibrations

Produces loud knocking sounds



**Gradient coils = Give position & shape to the image**

# RF coils:

Transmit radio waves

Receive the MRI signal

They work like a radio antenna.

✅ Two Types of RF Coils
Type	Function
Transmit (Tx)	Sends RF pulse
Receive (Rx)	Receives signal
Tx/Rx	Does both

✅ Usually:

Body coil = Transmitter

Surface coil = Receiver


✅ Function of RF Coil (Step-by-Step)

RF coil sends a 90° RF pulse

Protons absorb energy and tilt

Protons relax and emit signal

RF coil receives signal

Computer makes the image

✅ Types of RF Coils
| Coil              | Used For                       |
| ----------------- | ------------------------------ |
| Head coil         | Brain                          |
| Spine coil        | Spine                          |
| Knee coil         | Knee                           |
| Breast coil       | Breast                         |
| Surface coil      | Small body parts               |
| Phased array coil | Fast & high-resolution imaging |


✅ Key Properties
| Feature                        | Value |
| ------------------------------ | ----- |
| Produces RF waves              | ✅ Yes |
| Receives signal                | ✅ Yes |
| Produces magnetic field        | ❌ No  |
| Affects image quality directly | ✅ Yes |


**RF coils = Talk to protons and listen to their signal**

--------------------------------------------------------------------------------------

| Feature                        | Main Coil   | Gradient Coil | RF Coil  |
| ------------------------------ | ----------- | ------------- | -------- |
| Produces main magnetic field   | ✅ Yes       | ❌ No          | ❌ No     |
| Produces variable field        | ❌ No        | ✅ Yes         | ❌ No     |
| Sends RF energy                | ❌ No        | ❌ No          | ✅ Yes    |
| Receives MRI signal            | ❌ No        | ❌ No          | ✅ Yes    |
| Helps in spatial encoding      | ❌ No        | ✅ Yes         | ❌ No     |
| Always ON                      | ✅ Yes       | ❌ No          | ❌ No     |
| Directly affects image quality | ⚠️ Indirect | ⚠️ Indirect   | ✅ Direct |


```
Main coil → Creates the field

Gradient coil → Gives position

RF coil → Sends & receives signal
```