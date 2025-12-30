# HL7
HL7 (Health Level Seven) is an international standard for exchanging clinical and administrative healthcare data between hospital information systems.

## What HL7 Is Used For

HL7 is used to exchange text-based health information, not images.

Patient registration (ADT)

Orders (lab, radiology)

Reports and results

Billing and clinical updates

**- HL7 does NOT carry images — that’s the role of DICOM.**

## HL7 in Radiology

HIS / EHR
   ↓ (HL7 ADT / ORM)
RIS
   ↓
MRI Exam Performed
   ↓ (HL7 ORU)
RIS / EHR (Report & Status)

## Common HL7 Message Types
| Message | Purpose                                   |
| ------- | ----------------------------------------- |
| **ADT** | Admit, Discharge, Transfer (patient info) |
| **ORM** | Order message (MRI / CT request)          |
| **ORU** | Observation result (radiology report)     |

## HL7 vs DICOM
| HL7                  | DICOM                   |
| -------------------- | ----------------------- |
| Text & clinical data | Images & image metadata |
| Orders, reports      | Scans & pixels          |
| HIS ↔ RIS ↔ EHR      | MRI ↔ PACS              |

HL7 is a healthcare messaging standard used to exchange patient, order, and report information between hospital systems, while DICOM is used for medical images.