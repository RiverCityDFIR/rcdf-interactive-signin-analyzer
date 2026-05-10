# Getting Started

## Overview

The RCDF Interactive Sign-In Analyzer is designed to assist with review and analysis of Microsoft interactive sign-in telemetry.

The tool is intended to help investigators move from raw authentication logs to structured investigative output including detections, enrichment, timeline review, and reporting workflows.

---

## Basic Workflow

1. Download the latest release package
2. Extract the ZIP archive to a local directory
3. Launch the analyzer executable
4. Load a Microsoft interactive sign-in log export
5. Review detections, timelines, enrichment, and investigative pivots
6. Export reports or supporting files as needed

---

## Input Data

Recommended input format:

- Microsoft interactive sign-in log export
- CSV format
- Original column headers preserved
- Minimal manual modification before ingestion

---

## Evidence Handling

For forensic and investigative workflows:

- Preserve the original exported log file
- Work from a copy where appropriate
- Record source information and export timestamps
- Document examiner actions when required
- Retain associated hashes where relevant

The tool may display file hash information to assist with repeatability and evidence tracking workflows.

---

## Initial Review Areas

After loading a file, recommended review areas include:

- Flagged users
- Suspicious IP addresses
- New countries or ASNs
- Legacy authentication activity
- Success-after-failure sequences
- Client application changes
- Timeline reconstruction
- High and critical detections

---

## Exporting Results

Reports and supporting exports may include:

- Detection summaries
- Timeline output
- Investigative notes
- Enrichment results
- File metadata
- Hash information

Available export formats may vary by release version.

---

## Notes

Detection output is intended to assist investigative review and prioritization.

Findings should be validated against available evidence, tenant configuration, user activity, and additional supporting telemetry where appropriate.

IP Enrichment requires an internet connection.
