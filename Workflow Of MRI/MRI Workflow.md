# Workflow
Physician Order
      ↓
RIS (Scheduling, patient details)
      ↓
MRI Scan & Image Acquisition
      ↓
Image Reconstruction (FFT)
      ↓
PACS (Store, view, distribute images)
      ↓
Radiologist Reporting → RIS → EHR


# RIS — Before & During the Scan

- Radiology Information System (RIS) handles administrative and workflow tasks:

- Patient registration & demographics

- Exam scheduling & protocol selection

- Order management (who, what, when)

- Tracks scan status (scheduled → completed)

- Receives radiology reports

## Timing:

- Starts before the patient enters the MRI room

- Continues during and after the scan for reporting

# PACS — After Image Creation

- Picture Archiving and Communication System (PACS) manages images:

- Receives reconstructed MRI images

- Stores images long-term

- Enables viewing, comparison, and sharing

- Sends images to radiologists & clinicians

## Timing:

- Begins after MRI images are reconstructed

- Continues throughout diagnosis & follow-up

# How MRI, RIS, and PACS Talk

- Images are sent from MRI → PACS using DICOM

- Reports and patient info flow via HL7

# Summary 

RIS runs the exam, MRI makes the image, PACS stores and shows the image.

# 

┌──────────────────────────────┐
│ Physician Order / EHR (HIS)  │
└──────────────┬───────────────┘
               │  (HL7 Order)
               ↓
┌──────────────────────────────┐
│ RIS                          │
│ • Patient registration       │
│ • Scheduling                 │
│ • Exam protocol              │
│ • Worklist creation          │
└──────────────┬───────────────┘
               │  (DICOM MWL)
               ↓
┌──────────────────────────────┐
│ MRI Scanner                  │
│ • Proton alignment (B₀)      │
│ • RF excitation              │
│ • Signal acquisition         │
│ • k-space filling            │
│ • FFT reconstruction         │
└──────────────┬───────────────┘
               │  (DICOM Images)
               ↓
┌──────────────────────────────┐
│ PACS                         │
│ • Image storage              │
│ • Image viewing              │
│ • Distribution               │
│ • Comparison & archiving     │
└──────────────┬───────────────┘
               │
               ↓
┌──────────────────────────────┐
│ Radiologist Workstation      │
│ • Image interpretation       │
│ • Reporting                  │
└──────────────┬───────────────┘
               │  (HL7 Report)
               ↓
┌──────────────────────────────┐
│ RIS / EHR                    │
│ • Final report available     │
│ • Clinician access           │
└──────────────────────────────┘

RIS manages the exam workflow, MRI acquires and reconstructs images, PACS stores and distributes images, and reports return to RIS/EHR.