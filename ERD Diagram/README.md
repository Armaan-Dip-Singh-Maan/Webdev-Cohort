# ER Diagrams (Web Dev Cohort)

This folder contains Mermaid ER diagram sources (`.mmd`) and optional PNG/PDF exports for coursework submissions.

## Clinic ER Diagram

This folder contains a clean, scalable ER design for a clinic workflow:

- doctor and specialty management
- patient registration and repeat visits
- appointment booking and status tracking
- consultation/visit records
- diagnostic test ordering
- report generation after tests
- payment mapping to appointment and/or consultation

## Files

| Diagram | Mermaid source | Notes |
|--------|----------------|--------|
| Clinic | `clinic-erd.mmd` | Appointments, consultations, tests, reports, payments |
| Comic-Con parking | `comic-con-parking-erd.mmd` | Multi-zone parking, sessions, tickets, payments |
| Smart elevator | `smart-elevator-erd.mmd` | Multi-building lifts, requests, assignments, trip logs, maintenance |

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

---

## Comic-Con parking (event venue)

- Source: `comic-con-parking-erd.mmd` (exports: `comic-con-parking-erd.png`, `comic-con-parking-erd.pdf`).
- Zones and levels sit above parking spots; vehicles accumulate many `parking_sessions` over event days; spots host many sessions over time.
- Tickets are separate from sessions; payments attach to sessions; rate rules stay in `parking_rate_rules` instead of session rows.

---

## Smart elevator control (infrastructure monitoring)

- Source: `smart-elevator-erd.mmd` (exports: `smart-elevator-erd.png`, `smart-elevator-erd.pdf`).
- **Buildings** own **floors**, **shafts**, **service zones** (elevator banks), and **elevators**. Static elevator configuration (model, capacity, shaft) stays in `elevators`; **no ride telemetry** is stored there.
- **Elevator ↔ floor** service range is a junction (`elevator_floor_service`): many elevators can serve the same floor; one elevator serves many floors.
- **Floor requests** capture hall/car calls (`floor_requests`); **ride_assignments** link a request to exactly one elevator (`request_id` unique). Pending work is visible via `request_status` before an assignment exists.
- **Ride trip logs** (`ride_trip_logs`) hold completed movement analytics (from/to floors, timestamps, duration) and stay separate from configuration.
- **Elevator live state** is a dedicated 1:1 table for current `operational_status` and optional `current_floor_id` so status is not mixed with catalog fields.
- **Maintenance records** append per elevator (`maintenance_records`); history is never overwritten—temporary disable is reflected in live state plus open maintenance rows.
