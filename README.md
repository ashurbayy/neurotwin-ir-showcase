# NeuroTwin-IR

### Brain MRI analysis and digital tumor twin research

NeuroTwin-IR brings MRI review, tumor segmentation, 3D visualization, scenario exploration, and reporting into a single research workspace. Developed for TEKNOFEST 2026, it explores how imaging results can become easier to inspect, compare, and communicate.

**Research use only.** Not a medical device, diagnostic system, autonomous clinical decision system, or treatment recommendation engine.

## The problem

Imaging research often separates scan review, segmentation outputs, quantitative measurements, and reporting into disconnected steps. NeuroTwin-IR organizes those steps around the same case, keeping the relationship between inputs, model outputs, human review, and derived reports visible.

## The workflow

```text
MRI sequences
    ↓
Input validation and case association
    ↓
Five-fold segmentation pipeline
    ↓
2D / 3D review and versioned corrections
    ├── Region measurements → structured report
    └── Baseline geometry → scenario exploration
```

## Prototype capabilities

| Module | What it brings to the workflow |
| --- | --- |
| MRI intake | T1, T1CE, T2, and FLAIR NIfTI inputs associated with a case |
| Segmentation | A five-fold nnU-Net inference workflow with identifiable model artifacts |
| Image review | Multiplanar navigation, segmentation overlays, and 3D views |
| Region analysis | WT, TC, and ET measurements derived from segmentation masks |
| Human review | Separate AI-generated and human-corrected segmentation revisions |
| Digital twin | Day 0 geometry and standardized scenarios for days 30, 60, and 90 |
| Reports | Analysis-linked PDF output in Azerbaijani, Turkish, and English |

**WT** = whole tumor region · **TC** = tumor core · **ET** = enhancing tumor region. These are segmentation-region labels, not independent diagnoses.

## What the digital twin represents

The baseline comes from the case segmentation. Future views explore standardized growth scenarios conditioned on baseline geometry. They illustrate possible changes under selected assumptions; they are **not observed follow-up scans or validated patient-specific predictions**.

This distinction matters: a convincing 3D visualization is not evidence of predictive accuracy. Longitudinal validation remains a separate research task.

## System design

| Layer | Technologies and responsibility |
| --- | --- |
| Web workspace | Next.js, React, TypeScript, Tailwind CSS |
| Imaging viewer | NiiVue and NIfTI-based visualization |
| Application API | Python and FastAPI |
| Identity and structured data | Supabase Auth and PostgreSQL |
| Analysis workers | nnU-Net segmentation and GPU inference orchestration |
| Artifact storage | Private object storage and versioned derived outputs |

The implementation separates the web interface, application API, analysis workers, and storage. Model outputs and reports retain provenance rather than becoming disconnected screenshots or untraceable numbers.

## Engineering principles

- Keep model output distinct from human review.
- Preserve input lineage, pipeline identity, and checkpoint identity.
- Keep missing evidence explicit instead of manufacturing metrics.
- Keep credentials, imaging datasets, checkpoints, and identifiable information outside public Git repositories.
- Use synthetic or properly authorized de-identified material for demonstrations.

## Project status and access

This is a **public documentation showcase**, not the application source distribution. The implementation and model artifacts are maintained privately. It does not include patient files, credentials, training datasets, or model weights. Hosted demo availability is separate from this repository and is not guaranteed.

This overview describes the research prototype, not clinical readiness, regulatory approval, or a hospital integration.

## Research directions

Future work includes independent evaluation, stronger longitudinal validation, clearer uncertainty communication, and continued usability and performance testing. These are research directions, not completed claims.

---

Project portfolio: [Ashurbay Mammadzade](https://github.com/ashurbayy)
