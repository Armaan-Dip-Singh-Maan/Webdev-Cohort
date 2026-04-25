# Clinic ER Diagram

This folder contains a clean, scalable ER design for a clinic workflow:

- doctor and specialty management
- patient registration and repeat visits
- appointment booking and status tracking
- consultation/visit records
- diagnostic test ordering
- report generation after tests
- payment mapping to appointment and/or consultation

## Files

- `clinic-erd.mmd`: Mermaid ER diagram source file.

## Key Modeling Decisions

- `appointments` and `consultations` are separate entities.
  - An appointment can exist without a consultation (`BOOKED`, `CANCELLED`, `NO_SHOW`).
  - A consultation may link to an appointment for booked flow, but allows nullable link for walk-ins.
- Diagnostic tests are linked to `consultations` through `consultation_tests`.
  - This captures that tests are usually prescribed during a doctor visit.
  - One consultation can prescribe many tests.
- Reports are linked one-to-one with each ordered test entry (`consultation_tests`).
  - This preserves full traceability from patient -> visit -> prescribed test -> report.
- Doctor specialty is separated into a `specialties` table for better normalization and consistency.
- Payments are linked to `patient` and can reference `appointment` and/or `consultation`.
  - This supports real clinic billing scenarios (consultation-only, diagnostics-only, or bundled).

## How To Export

You can render `clinic-erd.mmd` in any Mermaid-compatible tool/editor and export to:

- PNG/JPG image
- PDF
- shared board link after import (Draw.io, Excalidraw, FigJam using Mermaid plugin/import flow)

## Relationship Coverage (Assignment Questions)

- Who are doctors and what specialties they have -> `doctors` + `specialties`
- Which patient booked which appointment -> `appointments.patient_id`
- Appointment status -> `appointments.status`
- Did appointment result in consultation -> optional 1:1 via `consultations.appointment_id`
- Were tests prescribed -> `consultation_tests`
- What reports were generated -> `test_reports`
- Can one patient have many visits -> yes, `patients 1:N consultations`
- Can one doctor attend many patients -> yes, via `consultations`
- Can one consultation lead to multiple tests -> yes, `consultations 1:N consultation_tests`
- How payments connect -> `payments` references patient and optional appointment/consultation
